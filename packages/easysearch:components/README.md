Easy Search Components
=====================

The components package adds helpful Blaze Templates to your app that cover a lot of basic functionality with extendibility 
and customization in mind. The `easy:search` package wraps this package together with `easysearch:core` for convenience. 

```html
<template name="searchBox">
  <!-- searchIndex typeof EasySearch.Index -->
  {{> EasySearch.Input index=searchIndex }}

  {{#EasySearch.IfInputEmpty index=searchIndex }}
    <div class="padded examples">Search to see the magic!</div>
  {{else}}
    {{#if resultsCount}}
      <div class="padded count-results">{{resultsCount}} results found.</div>
    {{/if}}
  {{/EasySearch.IfInputEmpty}}

  {{#EasySearch.IfSearching index=searchIndex }}
    <div>Searching...</div>
  {{/EasySearch.IfSearching }}  
  
  <ol class="leaderboard">
    {{#EasySearch.Each index=searchIndex }}
      ...
    {{/EasySearch.Each}}
  </ol>

  {{#EasySearch.IfNoResults index=searchIndex }}
    <div class="padded no-results">No results found</div>
  {{/EasySearch.IfNoResults }}
  
  {{> EasySearch.Pagination index=searchIndex maxPages=10 }}
</template>
```

## How to install

```sh
cd /path/to/project
meteor add easysearch:components
```
