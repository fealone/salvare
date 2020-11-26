# salvare
This tool is for sending directories to storage on clouds for backup.  
'salvare' means save in Latin.

## Help

```
Usage: salvare [TARGET] [OPTIONS]...

Target:
  Backup target

Options:
  -h, --help  Show this message and exit.
  -u, --upload-type [ENUM]  Select upload type [GCS, S3, Dropbox].
  -d, --destination [TEXT]  Destination path by upload type.
  -t, --tmpdir [TEXT]  The path used for writing with temporary.
  -n, --name [TEXT]  Used for the temporary file.
  -a, --access-token [TEXT]  Access token by upload type.
```

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

### S3

#### Required
* openssl
* base64

#### Commands

```bash
./salvare {BACKUP_DIRECTORY} --upload-type S3 --destination s3://{BUCKET}/{OBJECT} --access-key-id {ACCESS_KEY_ID} --secret-access-key {SECRET_ACCESS_KEY}
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
