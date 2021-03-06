---
title: "TopOne (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the top-rank record, where rank defines the ranking position of the event in the window according to the specified ordering."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea


ms.service: stream-analytics
ms.topic: reference
ms.assetid: 9728630c-1c59-4349-a562-fdd98433da9d
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# TopOne (Azure Stream Analytics)
  Returns the top-rank record, where rank defines the ranking position of the event in the window according to the specified ordering. Ordering/ranking is based on event columns and can be specified in ORDER BY clause.  
  
 ## Syntax  
  
```SQL   
TopOne() OVER (ORDER BY (<column name> [ASC |DESC])+)  
```  
  
## Arguments  
 **column_name**  
  
 Specifies the name of the column in the input event by which ordering will be done. Note that only ordering by bigint, float and datetime types are allowed.  
  
## Return Types  
 Returns a record.  
  
## Examples  
  
```SQL  
SELECT   
    TopOne() OVER (ORDER BY value DESC) as topEvent  
FROM input  
GROUP BY TumblingWindow(second, 10)  
  
```  
  
  
