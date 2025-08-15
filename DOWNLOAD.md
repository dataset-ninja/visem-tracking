Dataset **VISEM-Tracking** can be downloaded in [Supervisely format](https://developer.supervisely.com/api-references/supervisely-annotation-json-format):

 [Download](https://assets.supervisely.com/remote/eyJsaW5rIjogInMzOi8vc3VwZXJ2aXNlbHktZGF0YXNldHMvMzQzMV9WSVNFTS1UcmFja2luZy92aXNlbXRyYWNraW5nLURhdGFzZXROaW5qYS50YXIiLCAic2lnIjogIlArSGlqTnhMdm5zaEZBd3RMeUsraFRNN09oUGVBN29ETHVQdk9ZNGd0M1U9In0=?response-content-disposition=attachment%3B%20filename%3D%22visemtracking-DatasetNinja.tar%22)

As an alternative, it can be downloaded with *dataset-tools* package:
``` bash
pip install --upgrade dataset-tools
```

... using following python code:
``` python
import dataset_tools as dtools

dtools.download(dataset='VISEM-Tracking', dst_dir='~/dataset-ninja/')
```
Make sure not to overlook the [python code example](https://developer.supervisely.com/getting-started/python-sdk-tutorials/iterate-over-a-local-project) available on the Supervisely Developer Portal. It will give you a clear idea of how to effortlessly work with the downloaded dataset.

The data in original format can be [downloaded here](https://zenodo.org/records/7293726/files/VISEM-Tracking.zip?download=1).