---
title: Linkedin Metrics
---

<Details title='information'>

  This page show the last 360 days of interactions. 
  </Details>


```followers_by_date
SELECT 
    strptime(Fecha, '%Y-%m-%d %H:%M:%S') AS fecha,
    Nuevos_seguidores
FROM linkedin.followers
ORDER BY fecha ASC
LIMIT 60;

```
# Last 2 Months

<LineChart
    data={followers_by_date}
    x="fecha"
    y="Nuevos_seguidores"
    markers=true
    markerShape=emptyCircle
/>

# Interactions Overview

```interacciones_by_date
SELECT 
    strptime(Fecha, '%Y-%m-%d %H:%M:%S') AS fecha,
    Interacciones
FROM linkedin.interactions
ORDER BY fecha DESC
;
```


<LineChart
    data={interacciones_by_date}
    x="fecha"
    y="Interacciones"
    yAxisTitle="Interacciones"
/>

#  Impressions vs Members 


```general_metrics
SELECT 
*
FROM linkedin.general_metrics
;
```

<BarChart 
    data={general_metrics}
    x=Metrica
    y=Valor
    title="Comparison"
    labels=true
/>

#  Companies

```companies
SELECT
    Informacion AS category_type,
    Categoria AS category_name,
    CAST(regexp_replace(Valor, '%', '') AS INTEGER) AS percentage
FROM linkedin.other_info
WHERE Informacion = 'Sectores'
ORDER BY category_type, percentage DESC;
```

<DataTable data={companies}>
	<Column id=category_type title="Group" />
	<Column id=category_name title="Category" />
	<Column 
        id=percentage 
        title="Percentage" 
        align=center 
        contentType=bar 
    />
</DataTable>

## Let's connect:
- https://www.linkedin.com/in/fabricio-lennart/
- Deploy your project with [Evidence Cloud](https://evidence.dev/cloud)

