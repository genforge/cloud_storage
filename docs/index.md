# Cloud Storage Documentation

Cloud Storage extends the file utilities in a Frappe App to integrate with third-party cloud storage applications. Once configured, users can upload, download, or remove files to a cloud storage application via the Frappe App's interface. Depending on user permissions, they may also generate or reset sharing links to files.

Cloud Storage can be configured to work with a variety of cloud storage providers, including Amazon Web Services S3, DigitalOcean Spaces, and Backblaze B2.

See the following pages for detailed instructions on Cloud Storage installation and configuration:

- [Cloud Storage Developer Environment Installation](./development.md)
- [Cloud Storage Production Environment Installation](./production.md)
- [Cloud Storage Configuration](./configuration.md)

## Cloud Storage Quick Start

Once the Cloud Storage application is installed and configured, search for "File List" in the AwesomeBar. To upload a file, click the "+ Add File" button, load a file, and click "Upload". This action automatically adds the file to the configured third-party cloud storage application.

![Upload file dialogue box showing a new, non-private file called "Cloud_Storage.md" being uploaded to the system.](./assets/file_upload.png)

The page for the uploaded file includes several features. There's a button to "Download" the file from the cloud storage service, which will open a new browser window to the file's contents.

There's also a "Get Sharing Link" button that allows for a user to create a sharing link to the file for unauthenticated users. This only works if the user has permission to "Share" on File documents.

![Document view for the new file.](./assets/file_view.png)

The full link will appear in a dialogue box, and the link key saves to a "Sharing Link" field in the document. The link may be accessed any number of times again via the "Get Sharing Link" button.

![Sharing link dialogue box showing full link to the file in the cloud storage application.](./assets/sharing_link.png)

After a user generates a sharing link, they'll see a new "Reset Sharing Link" button. They can revoke the current sharing link by using the button to generate a new sharing link.

![New document view for a file after a sharing link is generated. There's a "Reset Sharing Link" button and a "Sharing Link" field with the current link key.](./assets/post_sharing_link.png)

Users may delete files as long as the file is not attached to a submitted document. When they delete a file in the Frappe interface, it is also removed from the cloud storage application.

If a user tries to access a file that's been deleted or clicks on the old version of a sharing link that's been reset, they will see the following error page.

![Error page when a file is no longer accessible.](./assets/reset_link_or_deleted_file_screen.png)

## Microsoft Word File Preview

Cloud Storage includes a feature that allows users to preview Microsoft Word files in the browser. This feature is enabled by default and works for local, remote and cloud storage files.

![Document view with a Microsoft Word file preview.](./assets/microsoft_word_preview.png)

## Multiple File Associations

Cloud Storage enhances Frappe's file system to allow for association of the same file with multiple documents.

This can be done by using the native "Attach" button. To select a File that has already been attached to the Frappe instance, you can select the 'Library' option. If you upload the file a second time -- where the file has an identical file hash -- Cloud Storage will associate the file with the same record.

When deleting attachments, if a File is associated with multiple records it must be remove intentionally from the record.
