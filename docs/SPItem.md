# SharePoint OAuth App Client
 
## SPItem

```

        $items = SPItem::getByTitle($list, "SitePagesTemplateV1");
        foreach ($items as $item){
            if($item["ID"] > 60)
                return $item;
        }
```
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
        
        try {
            $folder = SPFolder::getByRelativeUrl($this->spo, $folderName);
            $file = SPFile::getByName($folder, $fileName);
        } catch (\Exception $e){
            $file = null;
        }
        
        $spItem = $file->getSPItem();
        $spItem->update([
            "OData__ExtendedDescription" => 'sample description',
            "Semester" => 'sample semester,
            "Title" => 'sample title'
        ]);
        
```
