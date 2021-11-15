SortOrder: 1
## Filters
Both `Query` and `Count` APIs accepts the following filters:
* folderId
    * filter sites that are in no folder:
      ```
      { folderId: { $exists: false } }
      ```
    * filter sites that are in a specific folder:
      ```
      { folderId: '54915d80-62c2-4791-8483-88541ed18a60' }
      ```
* editorType
  ```
  { editorType: 'EDITOR' }
  ```
* appIds
    * filter sites that have provided app ids:
      ```
      { appIds: { $hasAll: ['1dbbce47-77b4-4ccf-be8c-8434eab7f58d', '87beaf91-cf01-4209-93ed-eb7cc47dc2cf' ] } }
      ```
    * filter sites that have at least one of the provided app ids:
      ```
      { appIds: { $hasSome: ['1dbbce47-77b4-4ccf-be8c-8434eab7f58d', '87beaf91-cf01-4209-93ed-eb7cc47dc2cf' ] } }
      ```
* premium
    ```
    { premium: true }
    ```
* published
  ```
  { published: true }
  ```
* namespace
  ```
  { namespace: 'WIX' }
  ```
* name
  ```
  { name: 'my-site' }
  ```
* state
  ```
  { state: 'ACTIVE' }
  ```
* domainConnected
  ```
  { domainConnected: true }
  ```

## Sorting
Sorting can be specified by the following fields:
* createdDate
* trashedDate
* updatedDate
* displayName
