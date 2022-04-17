Memo: Set up azure blob trigger function for dev.

(Assume you install azurite)

1. RUN:
   azurite --silent --lcation c:\azurite --debug c:\azurite\debug.log

2. local.settings.json:
   Add "BlobEndpoint":
   "AzureWebJobsStorage": "DefaultEndpointsProtocol=http;AccountName=devstoreaccount1;AccountKey=Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==;BlobEndpoint=http://127.0.0.1:10000/devstoreaccount1;QueueEndpoint=http://127.0.0.1:10001/devstoreaccount1;"

3. function.json:
   Change the path you want(Path should be blob container name)
   "bindings": [
   {
   "name": "myBlob",
   "type": "blobTrigger",
   "direction": "in",
   "path":"image-input",
   "connection": "AzureWebJobsStorage"
   }
   ]
