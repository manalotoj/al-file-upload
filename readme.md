<a name="module_al-file-upload"></a>
## al-file-upload
Supports a function to upload an input file to the AwardLetter Files API.***### Environment Requirements:* Internet access (port 80 and SSL over port 5443).* Node.js installed.### Installing directly from github:Clone or download as zip to local machine. For the later, unzip to desired location.In a command prompt at the root installation directory, execute *npm install* to install the followingmodule dependencies:Module              | Description--------------------|-------------------------------------------------------------------winston | Loggingpromise | JavaScript promiseoath-wrap | Request OAuth WRAP security tokens from an STSal-files-service | AwardLetter Files REST API### Configuration:All configuration is contained within the config.json file.**Logging:** The module is configured to log to a _logs_ folder within the root directory of the application.Standard log entries will be written to a file named alfilesystemwatcher.log while unhandled exceptions willbe logged to a file named alfilesystemwatchererrors.log.      "logging" : { "directory" : "./logs" }**Authorization:** The upload process requires an authorization token from a secure token service(STS).      "oauthWrapRequest" : { "url":"sts_url", "creds":{"uid":"userid", "pwd":"password"}, "wrapScope":"scope" }The following values must be provided in order to invoke the STS and acquire an authorization token:JSON Element | Description-------------|--------------------------------------------------------------------------url | The STS URLcreds.userid | User Idcreds.pwd | User passwordwrapScope | The resource that will be accessed using the authorization token.**AwardLetter Files API:** Defines the root URL of the AwardLetter Files API. This API defines a methodfor uploading AwardLetter input file content.      "filesApi" : { "rootUrl" : "root_url" }**File Format:** The file format being uploaded. Expected values include "txt" and "json".      "fileFormat" : "txt"###Running al-file-upload:Execute manually by opening a command prompt at the installation root directory:'		node al-file-upload.js [filepath]'		ex. node al-file-upload.js

