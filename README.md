---
services: data-lake-analytics
platforms: dotnet
author: saveenr
---

# U-SQL/Cognitive Imaging Face Detection Hello World

```
REFERENCE ASSEMBLY ImageCommon;
REFERENCE ASSEMBLY FaceSdk;
REFERENCE ASSEMBLY ImageEmotion;
REFERENCE ASSEMBLY ImageTagging;
REFERENCE ASSEMBLY ImageOcr;

@faces_from_extractor =
    EXTRACT FileName string, 
        NumFaces int, 
        FaceIndex int, 
        RectX float, RectY float, Width float, Height float, 
        FaceAge int, 
        FaceGender string
    FROM @"/usqlext/samples/cognition/{FileName}.jpg"
    USING new Cognition.Vision.FaceDetectionExtractor();
```

