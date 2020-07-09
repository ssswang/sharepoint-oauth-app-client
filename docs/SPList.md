# SharePoint OAuth App Client
 
## SPList
```
        $list = SPList::getByTitle($site, 'IT API Test List');

        $items = $list->getFields();
        //$items = $list->getSPItems();
        var_dump($items);
        //exit;
;       $list->createSPItem([
        "ApplicationInstanceId" => "50000001",
        "Title" => "Test 2",
        "UrlTest" => [
            //"odata.type" => "SP.FieldUrlValue",
            "Url" => "https://test.sharepoint.com/sites/test/IT%20API%20Test%20Library/Forms/AllItems.aspx?id=%2Fsites%2Fscs-test%2FIT%20API%20Test%20Library%2F2019%2F05%2F",
            "Description" =>  "Application File"
        ]]
            
            
      ```
