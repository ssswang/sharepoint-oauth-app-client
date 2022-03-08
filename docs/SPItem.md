# SharePoint OAuth App Client
 
## SPItem


Example update SPList item meta

```
        $settings = [
            'site' => [
                'resource' => env('SP_RESOURCE'),
                'client_id' => env('SP_CLIENT_ID'),
                'secret' => env('SP_SECRET'),
            ]
        ];

        // create a SharePoint Site instance
        $site = SPSite::create(env('SP_HOST'), $settings, true);

        // generate an Access Token (App-only Policy)
        $site->createSPAccessToken();
        $site->createSPFormDigest();
        
        // Get SPList
        
        $list = SPList::getByTitle($site, "list name");
        $listFields = $list->getFields();
        dump($listFields);
        
        // Get SPFile
        try {
            $folder = SPFolder::getByRelativeUrl($this->spo, $folderName);
            $file = SPFile::getByName($folder, $fileName);
        } catch (\Exception $e){
            $file = null;
        }
        // Get SPItem
        $spItem = $file->getSPItem();
        
        // Get SPItem field list
        $fields = $item->toArray();
        
        // Update SPItem
        $spItem->update([
            "OData__ExtendedDescription" => 'sample description',
            "Semester" => 'sample semester',
            "Title" => 'sample title'
        ]);
        
        // or
        
        $data = [
            "OData__ExtendedDescription" => 'sample description',
            "Semester" => 'sample semester,
            "Title" => 'sample title'
        ];
        
        $item = $list->getSPItem($fields["id"]);
        $guid = $item->getGUID();

        $list->updateSPItem($guid, $data);
        
```
