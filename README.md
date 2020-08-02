# JSON-Examples

A repo for testing various JSON payloads. 


## Testing in Swift 

1. Navigate to the `.json` file you're interested in using.
2. Copy the `JSON` contents. 
3. Back in your Xcode project create a new file, select `Empty` file in the Xcode new file template.
4. Create a file with a similar name e.g `presidents.json`
5. Save this file in your App navigation folder. 
6. Use the `Bundle` class to read the `.json` file and parse to your Swift object. 

> Make sure the past `JSON` contents start on line 1 in your new file. It won't be valid `JSON` if there are new lines or any comments about the first encountered `JSON` open bracket. 
