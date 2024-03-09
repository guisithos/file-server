Go application to upload files, delete existing files, and update existing files.

Features:

    Uploads files with size validation and type checking (supports jpeg, jpg, png, gif, and pdf).
    Generates random filenames to avoid conflicts.
    Stores uploaded files in a temporary directory.
    Provides endpoints for:
        Uploading files (/upload) - Accepts a multipart form data with a file named "uploadFile".
        Deleting files (/delete) - Requires a POST request with a form value named "fileName".
        Updating files (/update) - Requires a POST request with a form value named "uploadFile" and "fileName" (for the existing file to update).
    Serves uploaded files through a static file server (/files/).

Running the Application:

    Save the code as main.go.
    Run the application using go run main.go.
    Access the upload interface at http://localhost:8080/upload.

Using the Uploader:

    http://localhost:8080/upload in your browser.
    Select a file to upload.
    Click "Upload File".
    Upon successful upload, you'll receive a message with a link to access the uploaded file (/files/<filename>).

File Deletion:

    The frontend functionality for deletion is not yet implemented (requires JavaScript integration). However, you can manually delete files using the /delete endpoint.
    Send a POST request to http://localhost:8080/delete with a form value named "fileName" set to the filename of the file you want to delete.

File Update:

    Similar to deletion, the frontend functionality for updating files is not yet implemented.
    Send a POST request to http://localhost:8080/update with two form values:
        "uploadFile": The new file content to update the existing file with.
        "fileName": The filename of the existing file to update.
