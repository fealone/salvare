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

### Dropbox

#### Required
* curl

#### Commands

```bash
./salvare {BACKUP_DIRECTORY} -a {ACCESS_TOKEN} -u Dropbox -d {DEST_FULL_PATH}
```

#### Notes
* Get the access token via dropbox developers
    - https://www.dropbox.com/developers
* Required scope `files.content.write`
