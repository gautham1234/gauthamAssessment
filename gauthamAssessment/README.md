
# Spring-Boot-FIle-Upload-Rest-Service

1#. Using CURL
Single file upload
curl -F file=@"c:\\tmp\test1.txt" http://localhost:8383/api/fileupload

#Multiple file upload
curl -F files=@"c:\\tmp\test2.txt" -F files=@"c:\\tmp\test3.txt" http://localhost:8383/api/upload/multiplefiles

#Get uploaded files meta data, with output in JSON
curl http://localhost:8383/getFileUploadMetaData
[{
	"name": "test1.txt",
	"contentType": "text/plain",
	"contentSize": 15
}, {
	"name": "test2.txt",
	"contentType": "text/plain",
	"contentSize": 15
}]


2#. Using rest client (Google chrome plugins - Postman, Advanced Rest Client)
Single file upload
http://localhost:8383/api/fileupload
Request : POST
Attach file to upload with name as 'file' and its attachment
content-type will be auto detected, no need to mention

#Multi file upload
http://localhost:8383/api/upload/multiplefiles
Request : POST
Attach multiple files  and name them as 'files'
content-type will be auto detected, no need to mention

#Get uploaded files meta data, with output in JSON
curl http://localhost:8383/getFileUploadMetaData
Request : GET
[{
	"name": "test1.txt",
	"contentType": "text/plain",
	"contentSize": 15
}, {
	"name": "test2.txt",
	"contentType": "text/plain",
	"contentSize": 15
}]

