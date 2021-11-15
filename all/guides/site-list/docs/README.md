SortOrder: 0
# Site List

The Site List API is a service that holds all the public information about the sites accessible to a user, like the site's name, its URL, its publish status, when it was created, if the site has a premium plan attached to it, and more.
Users can also view their sites via the My Sites page, at https://manage.wix.com/account/sites.

## Objective
With the Site List API, you can `query` and `count` the list of sites in the account using specific `filters` and `sort` options.
Information provided for sites in the account includes their display name, publish status, editor type, premium status, owner, url, thumbnail and more.
You can filter sites by their folder ID, premium status, installed applications, domain connection status and more.

## Terminology
* Site: a website in the account. Sites are accessible to users according to the specific permissions they hold on a specific site or on the entire account.
* Folder: grouping of sites that account users can create to organize their sites. A site can only belong to one folder.

## Limitations
The maximal number of sites that can be retrieved by `QuerySites` is 1000.

## Business Scenario
* Channels: Import my sites into an external management system in which I can view and manage all of my sites from different providers.
* Channels: manage my workflow. Get a list of sites in a specific folder in order to later use the Folders API to move all of these sites into a different folder.

## User Flow
* To import my sites into an external management systemQuery all the sites in the account w/o filters.
* To query the list of sites in a folder: use the Folders API to resolve a folder’s name into an ID. In Site List API, use “query” and filter by FolderID. Use Folders API and move the returned list of sites to another folder.

## The Site object
The returned [Site](https://github.com/wix-private/sites-list/blob/master/sites-list-proto-api/src/main/proto/com/wixpress/sitelist/api/site.proto) object consists of the following properties:
* id
* htmlWebId
* name
* displayName
* createdDate
* trashedDate
* published
* premium
* viewUrl
* editUrl
* thumbnail
* ownerId
* contributorIds
* editorType
* blocked
* folderId
* namespace
* domainConnected
