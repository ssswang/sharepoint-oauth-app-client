# SharePoint OAuth App Client
 
## SPItem

```

        $items = SPItem::getByTitle($list, "SitePagesTemplateV1");
        foreach ($items as $item){
            if($item["ID"] > 60)
                return $item;
        }
        
```
