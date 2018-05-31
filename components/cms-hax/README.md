# CMS Integration for HAX
the `cms-hax` tag is an attempt to intentionally constrain the flexibility of HAX so that it can drop in and work quickly in a CMS environment. This is for CMS integrations where you want to place a tag on the page, put content in the slot of that tag and then have HAX "Just Work".

This project intentionally removes flexibility from the way it implements hax-body and associated tags to reduce HAX integrations to:
- get reference to the tag on the page
- wrap the tag around content
- add whatever autoloaded elements you need

This is a sample of what that would look like:
```
  <cms-hax open-default end-point="some/backend/endpoint" app-store-connection="sample-store.json">
    <lrn-table slot="autoloader"></lrn-table>
    <video-player slot="autoloader"></video-player>
    <h2>The heading to edit</h2>
    <p>A whole bunch of text that will be wrapped to edit</p>
  </cms-hax>

```


This is how the Drupal and Backdrop baseline integrations for HAX operate. In order to work with the `cms-token` tag in a lazy loading kind of pathless way, you can define the following global variable: `window.cmsTokenEndPoint="someplace/on/the/backend";`. See Drupal for an example of how this integrates with this tag.