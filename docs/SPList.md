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


            $list = SPList::getByTitle($this->spoSite, env("SP_WIKI_LIST"));
            $data = [
                "Title" => $name,
                "Code" => $iso,
                "Description" => "This is a page about".$name,
                "WikiField" => '<div class="ExternalClassF5ECBE6D7C9C45579F6CDEF212D102BB"><table id="layoutsTable"><tbody></tbody></table><span id="layoutsData" style="display:none;">false,false,1</span></div>',
            ];
            $item = $list->getSPItem($id);
            $fields = $list->getSPItemFields($id);
            dump($fields);
            $guid = $item->getGUID();
            $list->updateSPItem($guid, $data);
            $item = $list->getSPItem($id);
            
            
      ```
