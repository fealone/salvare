# salvare
This tool is for sending directories to storage on clouds for backup.  
'salvare' means save in Latin.

## Usage

### GCS

#### Required
* gcloud
* curl

#### Commands

```bash
export GOOGLE_APPLICATION_CREDENTIALS=credentials.json
./salvare {BACKUP_DIRECTORY} -u GCS -d gs://{BUCKET}/{OBJECT}
```
