# ![LOGO](logo.png) Street View Publish **flow**ground Connector

## Description

A generated **flow**ground connector for the Street View Publish API (version v1).

Generated from: https://api.apis.guru/v2/specs/googleapis.com/streetviewpublish/v1/swagger.json<br/>
Generated at: 2019-05-23T12:13:43+03:00

## API Description

Publishes 360 photos to Google Maps, along with position, orientation, and connectivity metadata. Apps can offer an interface for positioning, connecting, and uploading user-generated Street View images.


## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### After the client finishes uploading the photo with the returned<br/>
> UploadRef,<br/>
> CreatePhoto<br/>
> publishes the uploaded Photo to<br/>
> Street View on Google Maps.<br/>
> <br/>
> Currently, the only way to set heading, pitch, and roll in CreatePhoto is<br/>
> through the [Photo Sphere XMP<br/>
> metadata](https://developers.google.com/streetview/spherical-metadata) in<br/>
> the photo bytes. CreatePhoto ignores the  `pose.heading`, `pose.pitch`,<br/>
> `pose.roll`, `pose.altitude`, and `pose.level` fields in Pose.<br/>
> <br/>
> This method returns the following error codes:<br/>
> <br/>
> * google.rpc.Code.INVALID_ARGUMENT if the request is malformed or if<br/>
> the uploaded photo is not a 360 photo.<br/>
> * google.rpc.Code.NOT_FOUND if the upload reference does not exist.<br/>
> * google.rpc.Code.RESOURCE_EXHAUSTED if the account has reached the<br/>
> storage limit.

*Tags:* `photo`

#### Input Parameters
* `$.xgafv` - _optional_ - V1 error format.
    Possible values: 1, 2.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Updates the metadata of a Photo, such<br/>
> as pose, place association, connections, etc. Changing the pixels of a<br/>
> photo is not supported.<br/>
> <br/>
> Only the fields specified in the<br/>
> updateMask<br/>
> field are used. If `updateMask` is not present, the update applies to all<br/>
> fields.<br/>
> <br/>
> This method returns the following error codes:<br/>
> <br/>
> * google.rpc.Code.PERMISSION_DENIED if the requesting user did not<br/>
> create the requested photo.<br/>
> * google.rpc.Code.INVALID_ARGUMENT if the request is malformed.<br/>
> * google.rpc.Code.NOT_FOUND if the requested photo does not exist.<br/>
> * google.rpc.Code.UNAVAILABLE if the requested<br/>
> Photo is still being indexed.

*Tags:* `photo`

#### Input Parameters
* `id` - _required_ - Required. A unique identifier for a photo.
* `updateMask` - _optional_ - Mask that identifies fields on the photo metadata to update.
If not present, the old Photo
metadata is entirely replaced with the
new Photo metadata in this request.
The update fails if invalid fields are specified. Multiple fields can be
specified in a comma-delimited list.

The following fields are valid:

* `pose.heading`
* `pose.latLngPair`
* `pose.pitch`
* `pose.roll`
* `pose.level`
* `pose.altitude`
* `connections`
* `places`


<aside class="note"><b>Note:</b> When
updateMask
contains repeated fields, the entire set of repeated values get replaced
with the new contents. For example, if
updateMask
contains `connections` and `UpdatePhotoRequest.photo.connections` is empty,
all connections are removed.</aside>
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Deletes a Photo and its metadata.<br/>
> <br/>
> This method returns the following error codes:<br/>
> <br/>
> * google.rpc.Code.PERMISSION_DENIED if the requesting user did not<br/>
> create the requested photo.<br/>
> * google.rpc.Code.NOT_FOUND if the photo ID does not exist.

*Tags:* `photo`

#### Input Parameters
* `photoId` - _required_ - Required. ID of the Photo.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets the metadata of the specified<br/>
> Photo.<br/>
> <br/>
> This method returns the following error codes:<br/>
> <br/>
> * google.rpc.Code.PERMISSION_DENIED if the requesting user did not<br/>
> create the requested Photo.<br/>
> * google.rpc.Code.NOT_FOUND if the requested<br/>
> Photo does not exist.<br/>
> * google.rpc.Code.UNAVAILABLE if the requested<br/>
> Photo is still being indexed.

*Tags:* `photo`

#### Input Parameters
* `languageCode` - _optional_ - The BCP-47 language code, such as "en-US" or "sr-Latn". For more
information, see
http://www.unicode.org/reports/tr35/#Unicode_locale_identifier.
If language_code is unspecified, the user's language preference for Google
services is used.
* `photoId` - _required_ - Required. ID of the Photo.
* `view` - _optional_ - Specifies if a download URL for the photo bytes should be returned in the
Photo response.
    Possible values: BASIC, INCLUDE_DOWNLOAD_URL.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates an upload session to start uploading photo bytes.  The method uses<br/>
> the upload URL of the returned<br/>
> UploadRef to upload the bytes for<br/>
> the Photo.<br/>
> <br/>
> In addition to the photo requirements shown in<br/>
> https://support.google.com/maps/answer/7012050?hl=en&ref_topic=6275604,<br/>
> the photo must meet the following requirements:<br/>
> <br/>
> * Photo Sphere XMP metadata must be included in the photo medadata. See<br/>
> https://developers.google.com/streetview/spherical-metadata for the<br/>
> required fields.<br/>
> * The pixel size of the photo must meet the size requirements listed in<br/>
> https://support.google.com/maps/answer/7012050?hl=en&ref_topic=6275604, and<br/>
> the photo must be a full 360 horizontally.<br/>
> <br/>
> After the upload completes, the method uses<br/>
> UploadRef with<br/>
> CreatePhoto<br/>
> to create the Photo object entry.

*Tags:* `photo`

#### Input Parameters
* `$.xgafv` - _optional_ - V1 error format.
    Possible values: 1, 2.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Lists all the Photos that belong to<br/>
> the user.<br/>
> <br/>
> <aside class="note"><b>Note:</b> Recently created photos that are still<br/>
> being indexed are not returned in the response.</aside>

*Tags:* `photos`

#### Input Parameters
* `filter` - _optional_ - The filter expression. For example: `placeId=ChIJj61dQgK6j4AR4GeTYWZsKWw`.

The only filter supported at the moment is `placeId`.
* `languageCode` - _optional_ - The BCP-47 language code, such as "en-US" or "sr-Latn". For more
information, see
http://www.unicode.org/reports/tr35/#Unicode_locale_identifier.
If language_code is unspecified, the user's language preference for Google
services is used.
* `pageSize` - _optional_ - The maximum number of photos to return.
`pageSize` must be non-negative. If `pageSize` is zero or is not provided,
the default page size of 100 is used.
The number of photos returned in the response may be less than `pageSize`
if the number of photos that belong to the user is less than `pageSize`.
* `pageToken` - _optional_ - The
nextPageToken
value returned from a previous
ListPhotos
request, if any.
* `view` - _optional_ - Specifies if a download URL for the photos bytes should be returned in the
Photos response.
    Possible values: BASIC, INCLUDE_DOWNLOAD_URL.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Deletes a list of Photos and their<br/>
> metadata.<br/>
> <br/>
> Note that if<br/>
> BatchDeletePhotos<br/>
> fails, either critical fields are missing or there is an authentication<br/>
> error. Even if<br/>
> BatchDeletePhotos<br/>
> succeeds, individual photos in the batch may have failures.<br/>
> These failures are specified in each<br/>
> PhotoResponse.status<br/>
> in<br/>
> BatchDeletePhotosResponse.results.<br/>
> See<br/>
> DeletePhoto<br/>
> for specific failures that can occur per photo.

*Tags:* `photos`

#### Input Parameters
* `$.xgafv` - _optional_ - V1 error format.
    Possible values: 1, 2.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets the metadata of the specified<br/>
> Photo batch.<br/>
> <br/>
> Note that if<br/>
> BatchGetPhotos<br/>
> fails, either critical fields are missing or there is an authentication<br/>
> error. Even if<br/>
> BatchGetPhotos<br/>
> succeeds, individual photos in the batch may have failures.<br/>
> These failures are specified in each<br/>
> PhotoResponse.status<br/>
> in<br/>
> BatchGetPhotosResponse.results.<br/>
> See<br/>
> GetPhoto<br/>
> for specific failures that can occur per photo.

*Tags:* `photos`

#### Input Parameters
* `languageCode` - _optional_ - The BCP-47 language code, such as "en-US" or "sr-Latn". For more
information, see
http://www.unicode.org/reports/tr35/#Unicode_locale_identifier.
If language_code is unspecified, the user's language preference for Google
services is used.
* `photoIds` - _optional_ - Required. IDs of the Photos. For HTTP
GET requests, the URL query parameter should be
`photoIds=<id1>&photoIds=<id2>&...`.
* `view` - _optional_ - Specifies if a download URL for the photo bytes should be returned in the
Photo response.
    Possible values: BASIC, INCLUDE_DOWNLOAD_URL.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Updates the metadata of Photos, such<br/>
> as pose, place association, connections, etc. Changing the pixels of photos<br/>
> is not supported.<br/>
> <br/>
> Note that if<br/>
> BatchUpdatePhotos<br/>
> fails, either critical fields are missing or there is an authentication<br/>
> error. Even if<br/>
> BatchUpdatePhotos<br/>
> succeeds, individual photos in the batch may have failures.<br/>
> These failures are specified in each<br/>
> PhotoResponse.status<br/>
> in<br/>
> BatchUpdatePhotosResponse.results.<br/>
> See<br/>
> UpdatePhoto<br/>
> for specific failures that can occur per photo.<br/>
> <br/>
> Only the fields specified in<br/>
> updateMask<br/>
> field are used. If `updateMask` is not present, the update applies to all<br/>
> fields.<br/>
> <br/>
> The number of<br/>
> UpdatePhotoRequest<br/>
> messages in a<br/>
> BatchUpdatePhotosRequest<br/>
> must not exceed 20.<br/>
> <br/>
> <aside class="note"><b>Note:</b> To update<br/>
> Pose.altitude,<br/>
> Pose.latLngPair has to be<br/>
> filled as well. Otherwise, the request will fail.</aside>

*Tags:* `photos`

#### Input Parameters
* `$.xgafv` - _optional_ - V1 error format.
    Possible values: 1, 2.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

## License

**flow**ground :- Telekom iPaaS / googleapis-com-streetviewpublish-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
