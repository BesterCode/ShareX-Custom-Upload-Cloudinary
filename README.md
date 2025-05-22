# ShareX-Custom-Upload-Cloudinary
This works with a free account of Cloudinary.

### Step 1
You will need to find your "Cloud Name" in [Home](https://console.cloudinary.com/app/home) and your API Key in **Settings->Api Keys**.

### Step 2
Go to **Assets->Folders** and create a folder called `sharex`.<br>
![{A2BA2B4D-867C-4570-8CF6-8C47D671F457}](https://github.com/user-attachments/assets/ac2f2a22-e764-4478-bcce-232f45e62ed9)

### Step 3
Go to [Settings->Upload->Presets](https://console.cloudinary.com/app/settings/upload/presets) and create a preset called `sharex`.<br>
Set its Signing mode to `Unsigned` and Asset folder to `sharex` and **Save**.

### Configure ShareX

Go to **ShareX->Destinations->Custom Uploader Settings** and import these settings from clipboard:
```
{
  "Version": "17.0.0",
  "Name": "Cloudinary",
  "DestinationType": "ImageUploader",
  "RequestMethod": "POST",
  "RequestURL": "https://api.cloudinary.com/v1_1/CLOUD_NAME/image/upload",
  "Body": "MultipartFormData",
  "Arguments": {
    "file": "file",    
    "api_key": "API_KEY",
    "upload_preset": "sharex"
  },
  "FileFormName": "file",
  "URL": "{regex:.*\\\"url\\\":\"(.+?)\"|1}"
}
```

Change `CLOUD_NAME` and `API_KEY` to your real values.

In **ShareX->Destinations->Image Uploader** select **Custom image uploader**.<br>
If you want the URL to open after upload, select **ShareX->After upload tasks->Open URL**.
