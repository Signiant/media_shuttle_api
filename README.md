# media_shuttle_api

MediaShuttleApi - JavaScript client for media_shuttle_api
Signiant's **Media Shuttle Management API** endpoints allows you to automate portal and storage management and view active transfers using your own web applications.  The **System-to-Person API** allows you to create upload and download links directly from other applications, letting you accelerate file transfers through Media Shuttle.  For more information about getting started with the Media Shuttle API, read our [Getting Started Guide](http://developer.signiant.com/msapi/getting-started.html).  ---   You can test API endpoints using your Media Shuttle subscription by generating an API key from your IT Administration user menu, in the **Developer** section.  Once you have generated an API key, click the **Authorize** button, and enter your API key in the **Value** field, and click **Authorize** to enable the examples. 
This SDK is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 1.13.3
- Package version: 1.13.3
- Build package: io.swagger.codegen.languages.JavascriptClientCodegen

## Installation

### For [Node.js](https://nodejs.org/)

#### npm

To publish the library as a [npm](https://www.npmjs.com/),
please follow the procedure in ["Publishing npm packages"](https://docs.npmjs.com/getting-started/publishing-npm-packages).

Then install it via:

```shell
npm install media_shuttle_api --save
```

##### Local development

To use the library locally without publishing to a remote npm registry, first install the dependencies by changing 
into the directory containing `package.json` (and this README). Let's call this `JAVASCRIPT_CLIENT_DIR`. Then run:

```shell
npm install
```

Next, [link](https://docs.npmjs.com/cli/link) it globally in npm with the following, also from `JAVASCRIPT_CLIENT_DIR`:

```shell
npm link
```

Finally, switch to the directory you want to use your media_shuttle_api from, and run:

```shell
npm link /path/to/<JAVASCRIPT_CLIENT_DIR>
```

You should now be able to `require('media_shuttle_api')` in javascript files from the directory you ran the last 
command above from.

#### git
#
If the library is hosted at a git repository, e.g.
https://github.com/YOUR_USERNAME/media_shuttle_api
then install it via:

```shell
    npm install YOUR_USERNAME/media_shuttle_api --save
```

### For browser

The library also works in the browser environment via npm and [browserify](http://browserify.org/). After following
the above steps with Node.js and installing browserify with `npm install -g browserify`,
perform the following (assuming *main.js* is your entry file, that's to say your javascript file where you actually 
use this library):

```shell
browserify main.js > bundle.js
```

Then include *bundle.js* in the HTML pages.

### Webpack Configuration

Using Webpack you may encounter the following error: "Module not found: Error:
Cannot resolve module", most certainly you should disable AMD loader. Add/merge
the following section to your webpack config:

```javascript
module: {
  rules: [
    {
      parser: {
        amd: false
      }
    }
  ]
}
```

## Getting Started

Please follow the [installation](#installation) instruction and execute the following JS code:

```javascript
var MediaShuttleApi = require('media_shuttle_api');

var defaultClient = MediaShuttleApi.ApiClient.instance;

// Configure API key authorization: ApiKey
var ApiKey = defaultClient.authentications['ApiKey'];
ApiKey.apiKey = "YOUR API KEY"
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//ApiKey.apiKeyPrefix['Authorization'] = "Token"

var api = new MediaShuttleApi.PortalsApi()

var portalId = "portalId_example"; // {String} Unique portal identifier

var opts = { 
  'user': new MediaShuttleApi.PortalMember() // {PortalMember} The user email, role, and permissions to add to the portal
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
api.addUserToPortal(portalId, opts, callback);

```

## Documentation for API Endpoints

All URIs are relative to *https://api.mediashuttle.com/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*MediaShuttleApi.PortalsApi* | [**addUserToPortal**](docs/PortalsApi.md#addUserToPortal) | **POST** /portals/{portalId}/users | Add a user to a portal with a role and permissions
*MediaShuttleApi.PortalsApi* | [**assignStorageToPortal**](docs/PortalsApi.md#assignStorageToPortal) | **PUT** /portals/{portalId}/storage/{storageId} | Assign storage to a portal
*MediaShuttleApi.PortalsApi* | [**assignUserToPortal**](docs/PortalsApi.md#assignUserToPortal) | **PUT** /portals/{portalId}/users/{email} | Update the user's role and/or permissions
*MediaShuttleApi.PortalsApi* | [**createPortal**](docs/PortalsApi.md#createPortal) | **POST** /portals | Create a new portal
*MediaShuttleApi.PortalsApi* | [**getMembersFromPortal**](docs/PortalsApi.md#getMembersFromPortal) | **GET** /portals/{portalId}/users | Retrieve all members from a portal
*MediaShuttleApi.PortalsApi* | [**getPortalMember**](docs/PortalsApi.md#getPortalMember) | **GET** /portals/{portalId}/users/{email} | Fetch a portal member
*MediaShuttleApi.PortalsApi* | [**getPortalStorage**](docs/PortalsApi.md#getPortalStorage) | **GET** /portals/{portalId}/storage | List the storage locations assigned to a portal
*MediaShuttleApi.PortalsApi* | [**getPortals**](docs/PortalsApi.md#getPortals) | **GET** /portals | List portals
*MediaShuttleApi.PortalsApi* | [**removeUserFromPortal**](docs/PortalsApi.md#removeUserFromPortal) | **DELETE** /portals/{portalId}/users/{email} | Remove a user from a portal
*MediaShuttleApi.StorageApi* | [**createStorage**](docs/StorageApi.md#createStorage) | **POST** /storage | Create a new storage location
*MediaShuttleApi.StorageApi* | [**getStorage**](docs/StorageApi.md#getStorage) | **GET** /storage/{storageId} | Display information about a specific storage location
*MediaShuttleApi.StorageApi* | [**listStorage**](docs/StorageApi.md#listStorage) | **GET** /storage | List storage location
*MediaShuttleApi.SystemToPersonApi* | [**createPortalSubscription**](docs/SystemToPersonApi.md#createPortalSubscription) | **POST** /portals/{portalId}/subscriptions | Subscribe to portal events 
*MediaShuttleApi.SystemToPersonApi* | [**createToken**](docs/SystemToPersonApi.md#createToken) | **POST** /portals/{portalId}/packages/{packageId}/tokens | Create transfer link 
*MediaShuttleApi.SystemToPersonApi* | [**deletePortalSubscription**](docs/SystemToPersonApi.md#deletePortalSubscription) | **DELETE** /portals/{portalId}/subscriptions/{subscriptionId} | Delete a portal subscription 
*MediaShuttleApi.SystemToPersonApi* | [**getPackages**](docs/SystemToPersonApi.md#getPackages) | **GET** /portals/{portalId}/packages/{packageId} | Get package information 
*MediaShuttleApi.SystemToPersonApi* | [**getPortalSubscriptions**](docs/SystemToPersonApi.md#getPortalSubscriptions) | **GET** /portals/{portalId}/subscriptions | Get portal subscriptions 
*MediaShuttleApi.SystemToPersonApi* | [**portalsPortalIdPackagesPackageIdEventsGet**](docs/SystemToPersonApi.md#portalsPortalIdPackagesPackageIdEventsGet) | **GET** /portals/{portalId}/packages/{packageId}/events | Show package events 
*MediaShuttleApi.SystemToPersonApi* | [**portalsPortalIdPackagesPackageIdFilesGet**](docs/SystemToPersonApi.md#portalsPortalIdPackagesPackageIdFilesGet) | **GET** /portals/{portalId}/packages/{packageId}/files | Show package contents 
*MediaShuttleApi.SystemToPersonApi* | [**portalsPortalIdPackagesPost**](docs/SystemToPersonApi.md#portalsPortalIdPackagesPost) | **POST** /portals/{portalId}/packages | Create a new package 
*MediaShuttleApi.SystemToPersonApi* | [**putPackages**](docs/SystemToPersonApi.md#putPackages) | **PUT** /portals/{portalId}/packages/{packageId}/files | Add files to a package 
*MediaShuttleApi.TransfersApi* | [**getTransfers**](docs/TransfersApi.md#getTransfers) | **GET** /transfers | List current active transfers


## Documentation for Models

 - [MediaShuttleApi.AzureBlobStorage](docs/AzureBlobStorage.md)
 - [MediaShuttleApi.Error](docs/Error.md)
 - [MediaShuttleApi.FileRequest](docs/FileRequest.md)
 - [MediaShuttleApi.FileResponse](docs/FileResponse.md)
 - [MediaShuttleApi.FileSetRequest](docs/FileSetRequest.md)
 - [MediaShuttleApi.FileSetResponse](docs/FileSetResponse.md)
 - [MediaShuttleApi.LocalStorage](docs/LocalStorage.md)
 - [MediaShuttleApi.ModelPackage](docs/ModelPackage.md)
 - [MediaShuttleApi.PackageEventResponse](docs/PackageEventResponse.md)
 - [MediaShuttleApi.PackageEventSetResponse](docs/PackageEventSetResponse.md)
 - [MediaShuttleApi.PackageTokenRequest](docs/PackageTokenRequest.md)
 - [MediaShuttleApi.PackageTokenResponse](docs/PackageTokenResponse.md)
 - [MediaShuttleApi.Portal](docs/Portal.md)
 - [MediaShuttleApi.PortalFolder](docs/PortalFolder.md)
 - [MediaShuttleApi.PortalList](docs/PortalList.md)
 - [MediaShuttleApi.PortalMember](docs/PortalMember.md)
 - [MediaShuttleApi.PortalMemberRequest](docs/PortalMemberRequest.md)
 - [MediaShuttleApi.PortalMemberResponse](docs/PortalMemberResponse.md)
 - [MediaShuttleApi.PortalStorage](docs/PortalStorage.md)
 - [MediaShuttleApi.PortalStorageList](docs/PortalStorageList.md)
 - [MediaShuttleApi.PortalSubscriptionRequest](docs/PortalSubscriptionRequest.md)
 - [MediaShuttleApi.PortalSubscriptionResponse](docs/PortalSubscriptionResponse.md)
 - [MediaShuttleApi.PortalSubscriptionsResponse](docs/PortalSubscriptionsResponse.md)
 - [MediaShuttleApi.S3Storage](docs/S3Storage.md)
 - [MediaShuttleApi.Storage](docs/Storage.md)
 - [MediaShuttleApi.StorageList](docs/StorageList.md)
 - [MediaShuttleApi.Transfer](docs/Transfer.md)
 - [MediaShuttleApi.TransferList](docs/TransferList.md)
 - [MediaShuttleApi.User](docs/User.md)


## Documentation for Authorization


### ApiKey

- **Type**: API key
- **API key parameter name**: Authorization
- **Location**: HTTP header
