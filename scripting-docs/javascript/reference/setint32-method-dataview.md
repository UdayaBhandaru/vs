---
title: "setInt32 Method (DataView) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "DHTML"
ms.assetid: 07e5f068-0e3f-4c23-84b3-c72658d7f194
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# setInt32 Method (DataView)
Sets the Int32 value at the specified byte offset from the start of the view. There is no alignment constraint; multi-byte values may be set at any offset.  
  
## Syntax  
  
```  
dataView.setInt32 (byteOffset, value, littleEndian);   
```  
  
## Parameters  
 `byteOffset`  
 The place in the buffer at which the value should be retrieved.  
  
 `value`  
 The value to set.  
  
 `littleEndian`  
 Optional. If false or undefined, a big-endian value should be written, otherwise a little-endian value should be written.  
  
## Remarks  
 These methods raise an exception if they would write beyond the end of the view.  
  
## Example  
 The following example shows how to set the first Int32 in the DataView.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setInt32(0, 9);  
        }  
    }  
  
```  
  
## Requirements  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]