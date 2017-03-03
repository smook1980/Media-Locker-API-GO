# Getting started

## How to Build


* In order to successfully build and run your SDK files, you are required to have the following setup in your system:
    * **Go**  (Visit [https://golang.org/doc/install](https://golang.org/doc/install) for more details on how to install Go)
    * **Java VM** Version 8 or later
    * **Eclipse 4.6 (Neon)** or later ([http://www.eclipse.org/neon/](http://www.eclipse.org/neon/))
    * **GoClipse** setup within above installed Eclipse (Follow the instructions at [this link](https://github.com/GoClipse/goclipse/blob/latest/documentation/Installation.md#instructions) to setup GoClipse)
* Ensure that ```GOPATH``` environment variable is set in the system variables. If not, set it to your workspace directory where you will be adding your Go projects.
* The generated code uses unirest-go http library. Therefore, you will need internet access to resolve this dependency. If Go is properly installed and configured, run the following command to pull the dependency:

```Go
go get github.com/apimatic/unirest-go
```

This will install unirest-go in the ```GOPATH``` you specified in the system variables.

Now follow the steps mentioned below to build your SDK:

1. Open eclipse in the Go language perspective and click on the ```Import``` option in ```File``` menu.

![Importing SDK into Eclipse - Step 1](https://apidocs.io/illustration/go?step=import0)

2. Select ```General -> Existing Projects into Workspace``` option from the tree list.

![Importing SDK into Eclipse - Step 2](https://apidocs.io/illustration/go?step=import1)

3. In ```Select root directory```, provide path to the unzipped archive for the generated code. Once the path is set and the Project becomes visible under ```Projects``` click ```Finish```

![Importing SDK into Eclipse - Step 3](https://apidocs.io/illustration/go?step=import2&workspaceFolder=Media%20Locker%20API-GoLang&projectName=medialockerapi_lib)

4. The Go library will be imported and its files will be visible in the Project Explorer

![Importing SDK into Eclipse - Step 4](https://apidocs.io/illustration/go?step=import3&projectName=medialockerapi_lib)

## How to Use

The following section explains how to use the MedialockerapiLib library in a new project.

### 1. Add a new Test Project

Create a new project in Eclipse by ```File``` -> ```New``` -> ```Go Project```

![Add a new project in Eclipse](https://apidocs.io/illustration/go?step=createNewProject0)

Name the Project as ```Test``` and click ```Finish```

![Create a new Maven Project - Step 1](https://apidocs.io/illustration/go?step=createNewProject1)

Create a new directory in the ```src``` directory of this project

![Create a new Maven Project - Step 2](https://apidocs.io/illustration/go?step=createNewProject2&projectName=medialockerapi_lib)

Name it ```test.com```

![Create a new Maven Project - Step 3](https://apidocs.io/illustration/go?step=createNewProject3&projectName=medialockerapi_lib)

Now create a new file inside ```src/test.com```

![Create a new Maven Project - Step 4](https://apidocs.io/illustration/go?step=createNewProject4&projectName=medialockerapi_lib)

Name it ```testsdk.go```

![Create a new Maven Project - Step 5](https://apidocs.io/illustration/go?step=createNewProject5&projectName=medialockerapi_lib)

In this Go file, you can start adding code to initialize the client library. Sample code to initialize the client library and using its methods is given in the subsequent sections.

### 2. Configure the Test Project

You need to import your generated library in this project in order to make use of its functions. In order to import the library, you can add its path in the ```GOPATH``` for this project. Follow the below steps:

Right click on the project name and click on ```Properties```

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/go?step=testProject0&projectName=medialockerapi_lib)

Choose ```Go Compiler``` from the side menu. Check ```Use project specific settings``` and uncheck ```Use same value as the GOPATH environment variable.```. By default, the GOPATH value from the environment variables will be visible in ```Eclipse GOPATH```. Do not remove this as this points to the unirest dependency.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/go?step=testProject1)

Append the library path to this GOPATH

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/go?step=testProject2&workspaceFolder=Media%20Locker%20API-GoLang)

Once the path is appended, click on ```OK```

### 3. Build the Test Project

Right click on the project name and click on ```Build Project```

![Build Project](https://apidocs.io/illustration/go?step=buildProject&projectName=medialockerapi_lib)

### 4. Run the Test Project

If the build is successful, right click on your Go file and click on ```Run As``` -> ```Go Application```

![Run Project](https://apidocs.io/illustration/go?step=runProject&projectName=medialockerapi_lib)

## Class Reference

### <a name="list_of_controllers"></a>List of Controllers

* [api_pkg](#api_pkg)

### <a name="api_pkg"></a>![Class: ](https://apidocs.io/img/class.png ".api_pkg") api_pkg

#### Get instance

Factory for the ``` API ``` interface can be accessed from the package api_pkg.

```go
aPI := api_pkg.NewAPI()
```

#### <a name="add_media_item"></a>![Method: ](https://apidocs.io/img/method.png ".api_pkg.AddMediaItem") AddMediaItem

> *Tags:*  ``` Skips Authentication ``` 

> create a new media item to be uploaded


```go
func (me *API_IMPL) AddMediaItem(mediaItem *models_pkg.MediaItem)([]*models_pkg.MediaItem,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mediaItem |  ``` Required ```  | Media Item metadata |


#### Example Usage

```go
var mediaItem *models_pkg.MediaItem

var result []*models_pkg.MediaItem
result,_ = aPI.AddMediaItem(mediaItem)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | invalid input, object invalid |
| 409 | an existing item already exists |
| 500 | unexpected error |



#### <a name="get_library_index"></a>![Method: ](https://apidocs.io/img/method.png ".api_pkg.GetLibraryIndex") GetLibraryIndex

> *Tags:*  ``` Skips Authentication ``` 

> List the media library items.


```go
func (me *API_IMPL) GetLibraryIndex(
            offset *int64,
            limit *int64)([]*models_pkg.MediaItem,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | start listing at given offset |
| limit |  ``` Optional ```  | the maximum number of items to list |


#### Example Usage

```go
offset,_ := strconv.ParseInt("146", 10, 8)
limit,_ := strconv.ParseInt("146", 10, 8)

var result []*models_pkg.MediaItem
result,_ = aPI.GetLibraryIndex(offset, limit)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | bad input parameter |



[Back to List of Controllers](#list_of_controllers)



