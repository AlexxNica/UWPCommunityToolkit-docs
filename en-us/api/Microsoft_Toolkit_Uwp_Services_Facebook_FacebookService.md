---
permalink: /en-US/api/Microsoft_Toolkit_Uwp_Services_Facebook_FacebookService.htm
title: Microsoft.Toolkit.Uwp.Services.Facebook.FacebookService API 
description: API page for Microsoft.Toolkit.Uwp.Services.Facebook.FacebookService
keywords: windows, app, toolkit, UWP, API
layout: default
search.product: eADQiWindows 10XVcnh
---


# FacebookService class

Class for connecting to Facebook.

## Members

The **FacebookService** class has this types of members

* [constructors](#constructors)

* [methods](#methods)

* [properties](#properties)

* [fields](#fields)

### constructors

#### contructor

Initializes a new instance of the [FacebookService](Microsoft_Toolkit_Uwp_Services_Facebook_FacebookService.htm) class. Default private constructor.



### methods

#### Initialize(System.String appId,Microsoft.Toolkit.Uwp.Services.Facebook.FacebookPermissions requiredPermissions,System.String windowsStoreId)

Initialize underlying provider with relevent token information.

##### parameters



| name | description | type |


#### PostToFeedWithDialogAsync(System.String title,System.String description,System.String link,System.String pictureUrl)

Enables posting data to the timeline using Facebook dialog.

##### parameters



| name | description | type |


#### ProcessResultsAsync(System.Collections.Generic.IReadOnlyList(System.Object) results,System.Int32 maxRecords)

Helper method to process pages of results from underlying service instance.

##### parameters



| name | description | type |


#### Initialize(Microsoft.Toolkit.Uwp.Services.Facebook.FacebookOAuthTokens oAuthTokens,Microsoft.Toolkit.Uwp.Services.Facebook.FacebookPermissions requiredPermissions)

Initialize underlying provider with relevent token information.

##### parameters



| name | description | type |


#### PostPictureToFeedAsync(System.String title,System.String pictureName,Windows.Storage.Streams.IRandomAccessStreamWithContentType pictureStream)

Enables posting a picture to the timeline

##### parameters



| name | description | type |


#### PostToFeedAsync(System.String title,System.String message,System.String description,System.String link,System.String pictureUrl)

Enables direct posting data to the timeline.

##### parameters



| name | description | type |


#### GetUserPictureInfoAsync()

Returns the [FacebookPicture](Microsoft_Toolkit_Uwp_Services_Facebook_FacebookPicture.htm) object associated with the logged user

##### parameters



| name | description | type |


#### LoginAsync()

Login with set of required requiredPermissions.

##### parameters



| name | description | type |


#### LogoutAsync()

Log out of the underlying service instance.

##### parameters



| name | description | type |


#### RequestAsync(Microsoft.Toolkit.Uwp.Services.Facebook.FacebookDataConfig config,System.Int32 maxRecords)

Request list data from service provider based upon a given config / query.

##### parameters



| name | description | type |


### properties

#### LoggedUser

Gets the current logged user name.



#### WindowsStoreId

Gets a Windows Store ID associated with the current app



#### Instance

Gets public singleton property.



#### Provider

Gets a reference to an instance of the underlying data provider.



### fields

#### paginatedArray

Reference to paginated array object for handling multiple pages of returned service list data.



#### instance

Private singleton field.



#### permissions

List of permissions required by the app.



#### queryResults

Strongly typed list of service query data.



#### isInitialized

Field for tracking initialization status.

