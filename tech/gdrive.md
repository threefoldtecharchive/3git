# Gdrive tool

This tool provides endpoints for downloading and serving gdrive documents, spreadsheets or presentations and specific slides which can be used from wikis.

## Available endpoints
The current endpoints will get a pdf version of any document, spreadsheets or presentation and a png of any specific slide

- `/wiki/gdrive/document/{doc_guid}`: for documents (pdf)
- `/wiki/gdrive/{presentation_guid}`: for full presentation (pdf)
- `/wiki/gdrive/slide/{presentation_guid}/{slide_guid}`: for specific slide of presentation (png)
- `/wiki/gdrive/spreadsheets/{sheet_guid}`: for spreadsheets (pdf)

## How to Configure
Before setting up needed configuration, you need to [setup a service account for google apis](#setting-up-service-account-for-google-apis), then follow the following steps:

1- Configure the main instance of gdrive client and make sure to provide a credentials file with the correct permissions

```python
cl = j.clients.gdrive.main
cl.credfile = "{path_to_cred_file}"
cl.save()
```

2- Create the needed directories to store the files
```bash
mkdir -p /sandbox/var/gdrive/static/{document,spreadsheets,presentation,slide}
```

## Setting up service account for google apis

See how to setup a [service account](service_account.md) for different google apis, as it's required by other macros.


