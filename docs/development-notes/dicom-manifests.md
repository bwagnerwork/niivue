# DICOM Manifest
A DICOM manifest is a text file that contains a list of relative URLs of DICOM files. When a manifest file is specified in the image options using the isManifest property Niivue will use the URL as a relative URL to download DICOM files.

If no file name is specified in the URL, Niivue will append niivue-manifest.txt.  A custom file can be used, but it must have a .txt extension.

Check out this [example](https://github.com/niivue/niivue-demo-images/blob/main/dicom/niivue-manifest.txt) to see how DICOM files should be listed.

```javascript
import * as niivue from './niivue.es.js'
     var volumeList1 = [       
         {
           url: "https://raw.githubusercontent.com/niivue/niivue-demo-images/main/dicom/niivue-manifest.txt",
           colorMap: "gray",
           opacity: 1,
           visible: true,
           isManifest: true,
         },
        ] 
      var nv1 = new niivue.Niivue()
      nv1.setRadiologicalConvention(false)
      nv1.attachTo('gl1')
      nv1.loadVolumes(volumeList1)
      nv1.setSliceType(nv1.sliceTypeMultiplanar)
```
