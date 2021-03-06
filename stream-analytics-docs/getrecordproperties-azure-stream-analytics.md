---
title: "GetRecordProperties (Azure Stream Analytics) | Microsoft Docs"
description: "Returns a dataset with record property names and values."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea


ms.service: stream-analytics
ms.topic: reference
ms.assetid: 7720ce57-0ef0-406d-84ba-352af8d2dadf
caps.latest.revision: 7
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# GetRecordProperties (Azure Stream Analytics)
  Returns a dataset with record property names and values. The result of the GetRecordProperties function must be used with the [CROSS APPLY](apply-azure-stream-analytics.md) operator.  
  
 ## Syntax  
  
```SQL   
GetRecordProperties ( column_reference )  
```  
  
## Arguments  
 **Column_reference**  
  
 Is the column reference expression to be evaluated. Column must be of type Record  
  
## Return Types  
 Returns a dataset with PropertyName and PropertyValue columns.  
  
## Examples  
  
```SQL  
SELECT   
    recordProperty.PropertyName,  
    recordProperty.PropertyValue  
FROM input as event  
CROSS APPLY GetRecordProperties(event.recordField) AS recordProperty  
```  
  

