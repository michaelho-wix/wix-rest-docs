SortOrder: 0
# Site List

The Site List API is a service that holds all the public information about the sites accessible to a user, like the site's name, its URL, its publish status, when it was created, if the site has a premium plan attached to it, and more.
Users can also view their sites via the `My Sites` page, at https://manage.wix.com/account/sites.

## Objective
With the Site List API, you can `query` and `count` the list of sites in the account using specific `filters` and `sort` options.
Information provided for sites in the account includes their display name, publish status, editor type, premium status, owner, url, thumbnail and more.
You can filter sites by their folder ID, premium status, installed applications, domain connection status and more.

## Target Audience 
* Channels users use an external system to view and manage sites. They would use this API to sync their sites’ statuses with their external records.
* Channels would use it for sales optimization by querying the list of sites that are not yet premium.

## Terminology
* **Site**:  a website in the account. Sites are accessible to users according to the specific permissions they hold on a specific site or on the entire account.
* **Folder**: grouping of sites that account users can create to organize their sites. A site can only belong to one folder.
* **Account**: a wix account can have one or more users. Standard accounts have one user while team accounts can have multiple users.
* **User**: a user represents a member of a Wix account. Each user has its own email and password that is used to access Wix.

## Limitations
The maximal number of sites that can be retrieved by `QuerySites` is 1000.

## Business Scenario
* Channels: Import my sites into an external management system in which I can view and manage all of my sites from different providers.
* Channels: display the number of sites in each folder in an external management system by counting the number of sites in a folder.
* Channels: manage my workflow. Get a list of sites in a specific folder in order to later use the Folders API to move all of these sites into a different folder. You can a count of the number of sites in each folder in order to know how many sites are in a specific workflow step.

## User Flow
1. To import my sites into an external management system: Query all the sites in the account without any filters.
2. To count the number of sites in a folder, use `count` and filter by FolderID.
3. To query the list of sites in a folder: use `query` and filter by FolderID.

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
