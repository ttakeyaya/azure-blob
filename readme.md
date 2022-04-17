Local dev for azure blobtrigger

1. azurite --silent --lcation c:\azurite --debug c:\azurite\debug.log

2. local.settings.json
   "AzureWebJobsStorage": "DefaultEndpointsProtocol=http;AccountName=devstoreaccount1;AccountKey=Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==;BlobEndpoint=http://127.0.0.1:10000/devstoreaccount1;QueueEndpoint=http://127.0.0.1:10001/devstoreaccount1;"

3. function.json
   "bindings": [
   {
   "name": "myBlob",
   "type": "blobTrigger",
   "direction": "in",
   "path":"image-input",
   "connection": "AzureWebJobsStorage"
   }
   ]

"path" should be blob container name
