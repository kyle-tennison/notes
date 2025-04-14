# OnPy Debugging

Response from `https://cad.onshape.com/api/v10/documents/d/e4e1c6e187a1e19d9bbe9ecb/w/ebce6e23f81f69779816e8ca/elements`

```json
[
  {
    "name": "Part Studio 1",
    "id": "178ecee86dc1c9fc3d1ed888",
    "type": "Part Studio",
    "elementType": "PARTSTUDIO",
    "filename": null,
    "thumbnails": null,
    "thumbnailInfo": null,
    "dataType": "onshape/partstudio",
    "microversionId": "bd139b16b6aa07231b448dfd",
    "applicationTarget": null,
    "foreignDataId": null,
    "unupdatable": false,
    "safeToShow": true,
    "specifiedUnit": null,
    "prettyType": null,
    "zip": null,
    "lengthUnits": "inch",
    "angleUnits": "degree",
    "massUnits": "pound",
    "timeUnits": "second",
    "forceUnits": "poundForce",
    "pressureUnits": "poundPerSquareInch",
    "momentUnits": "inchPound",
    "accelerationUnits": "inchPerSecondSquared",
    "angularVelocityUnits": "degreePerSecond",
    "energyUnits": "footPoundForce",
    "areaUnits": "squareInch",
    "volumeUnits": "cubicInch"
  },
  {
    "name": "Assembly 1",
    "id": "36b33c70482a041198d4bbc2",
    "type": "Assembly",
    "elementType": "ASSEMBLY",
    "filename": null,
    "thumbnails": null,
    "thumbnailInfo": null,
    "dataType": "onshape/assembly",
    "microversionId": "09126d25bf2f15ea4e6f5b48",
    "applicationTarget": null,
    "foreignDataId": null,
    "unupdatable": false,
    "safeToShow": true,
    "specifiedUnit": null,
    "prettyType": null,
    "zip": null,
    "lengthUnits": "inch",
    "angleUnits": "degree",
    "massUnits": "pound",
    "timeUnits": "second",
    "forceUnits": "poundForce",
    "pressureUnits": "poundPerSquareInch",
    "momentUnits": "inchPound",
    "accelerationUnits": "inchPerSecondSquared",
    "angularVelocityUnits": "degreePerSecond",
    "energyUnits": "footPoundForce",
    "areaUnits": "squareInch",
    "volumeUnits": "cubicInch"
  }
]
```

Target part studio `178ecee86dc1c9fc3d1ed888`:

Response from calling:

```
https://cad.onshape.com/api/v10/partstudios/d/e4e1c6e187a1e19d9bbe9ecb/w/ebce6e23f81f69779816e8ca/e/178ecee86dc1c9fc3d1ed888/features
```

```json
{
  "btType": "BTFeatureListResponse-2457",
  "serializationVersion": "1.2.7",
  "isComplete": true,
  "rollbackIndex": 1,
  "features": [
    {
      "btType": "BTMSketch-151",
      "constraints": [
        {
          "btType": "BTMSketchConstraint-2",
          "hasOffsetData1": false,
          "offsetOrientation1": false,
          "offsetDistance1": 0,
          "hasOffsetData2": false,
          "offsetOrientation2": false,
          "offsetDistance2": 0,
          "hasPierceParameter": false,
          "pierceParameter": 0,
          "helpParameters": [],
          "constraintType": "COINCIDENT",
          "parameters": [
            {
              "btType": "BTMParameterString-149",
              "value": "4itT1mOTkpCa.center",
              "nodeId": "M2HuLJ/cAzjQsdzKb",
              "parameterId": "localFirst"
            },
            {
              "btType": "BTMParameterQueryList-148",
              "queries": [
                {
                  "btType": "BTMIndividualQuery-138",
                  "queryStatement": null,
                  "queryString": "",
                  "nodeId": "Mpjo5vspy4l5/oVxR"
                }
              ],
              "nodeId": "MOKybYlwuEi6Bk3Cz",
              "parameterId": "externalSecond"
            }
          ],
          "namespace": "",
          "nodeId": "MyeXmaQc6wd3J9Xxa",
          "index": 1,
          "entityId": "4itT1mOTkpCa.centerSnap0"
        }
      ],
      "entities": [
        {
          "btType": "BTMSketchCurve-4",
          "geometry": {
            "btType": "BTCurveGeometryCircle-115",
            "radius": 0.05616815669829466,
            "clockwise": false,
            "yCenter": 0,
            "xDir": 1,
            "yDir": 0,
            "xCenter": 0
          },
          "centerId": "4itT1mOTkpCa.center",
          "internalIds": [],
          "isConstruction": false,
          "isFromSplineHandle": false,
          "isFromSplineControlPolygon": false,
          "isFromEndpointSplineHandle": false,
          "parameters": [],
          "namespace": "",
          "nodeId": "MWKZq1FCrKqQttfjm",
          "index": 1,
          "entityId": "4itT1mOTkpCa"
        }
      ],
      "namespace": "",
      "name": "Sketch 1",
      "suppressed": false,
      "parameters": [
        {
          "btType": "BTMParameterQueryList-148",
          "queries": [
            {
              "btType": "BTMIndividualQuery-138",
              "queryStatement": null,
              "queryString": "query=qCompressed(1.0,\"%B5$QueryM4Sa$entityTypeBa$EntityTypeS4$FACESb$historyTypeS8$CREATIONSb$operationIdB2$IdA1S3.7$TopplaneOpS9$queryTypeS5$DUMMY\",id);",
              "nodeId": "FdZtBmuX5FmIIsG"
            }
          ],
          "nodeId": "kT/aXEc+t7Om7M1J",
          "parameterId": "sketchPlane"
        },
        {
          "btType": "BTMParameterBoolean-144",
          "value": false,
          "nodeId": "RTo/mVrvntZBEODg",
          "parameterId": "disableImprinting"
        }
      ],
      "featureId": "FqYhJLVKK3IMjPe_0",
      "nodeId": "LGVmx56rE3+CIEFe",
      "featureType": "newSketch",
      "returnAfterSubfeatures": false,
      "subFeatures": []
    }
  ],
  "sourceMicroversion": "490c311ed1af49bb5ff33227",
  "microversionSkew": false,
  "rejectMicroversionSkew": false,
  "featureStates": {
    "Origin": {
      "btType": "BTFeatureState-1688",
      "featureStatus": "OK",
      "inactive": false
    },
    "Top": {
      "btType": "BTFeatureState-1688",
      "featureStatus": "OK",
      "inactive": false
    },
    "Front": {
      "btType": "BTFeatureState-1688",
      "featureStatus": "OK",
      "inactive": false
    },
    "Right": {
      "btType": "BTFeatureState-1688",
      "featureStatus": "OK",
      "inactive": false
    },
    "FqYhJLVKK3IMjPe_0": {
      "btType": "BTFeatureState-1688",
      "featureStatus": "OK",
      "inactive": false
    }
  },
  "imports": [
    {
      "btType": "BTMImport-136",
      "namespace": "",
      "nodeId": "MY9cQXIj1kgvYf3N8",
      "path": "onshape/std/geometry.fs",
      "version": "2559.0"
    }
  ],
  "libraryVersion": 2559,
  "defaultFeatures": [
    {
      "btType": "BTMFeature-134",
      "namespace": "",
      "name": "Origin",
      "suppressed": false,
      "parameters": [],
      "featureId": "Origin",
      "nodeId": "MPAav4tOsxnKmXyMe",
      "featureType": "origin",
      "returnAfterSubfeatures": false,
      "subFeatures": []
    },
    {
      "btType": "BTMFeature-134",
      "namespace": "",
      "name": "Top",
      "suppressed": false,
      "parameters": [],
      "featureId": "Top",
      "nodeId": "M54JyTA4ktKcRF9bt",
      "featureType": "defaultPlane",
      "returnAfterSubfeatures": false,
      "subFeatures": []
    },
    {
      "btType": "BTMFeature-134",
      "namespace": "",
      "name": "Front",
      "suppressed": false,
      "parameters": [],
      "featureId": "Front",
      "nodeId": "MATYNySFByazBZbVO",
      "featureType": "defaultPlane",
      "returnAfterSubfeatures": false,
      "subFeatures": []
    },
    {
      "btType": "BTMFeature-134",
      "namespace": "",
      "name": "Right",
      "suppressed": false,
      "parameters": [],
      "featureId": "Right",
      "nodeId": "MZLeZYw+xa3caL9pe",
      "featureType": "defaultPlane",
      "returnAfterSubfeatures": false,
      "subFeatures": []
    }
  ]
}
```