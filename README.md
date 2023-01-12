> Where I put some excerpts that I use or that I have already used for backup


###### REDIS

$Redis = new RedisService();

```php
$Redis->set('demo', 'demo');
$Redis->get('demo');
$Redis->del('demo');
$Redis->exists('demo');
```

------------

###### Functions

//Exchange special characters
```javascript
ReplaceCharSet(html: string) {
  html = html.replace(/[“”‘’]/g, '"');
  html.replace(/(___+)\w/g, decodeURI("<hr>"));
  html.replace(/(___+)\w/g, decodeURI("<hr>"));
  return html;
}
```

//Remove accent 
```javascript
RemoveAccentuation(term: string) {
  var mapaAcentosHex = {
    a: /[\xE0-\xE6]/g,
    e: /[\xE8-\xEB]/g,
    i: /[\xEC-\xEF]/g,
    o: /[\xF2-\xF6]/g,
    u: /[\xF9-\xFC]/g,
    c: /\xE7/g,
    n: /\xF1/g
  };
  for (var letra in mapaAcentosHex) {
    var expressaoRegular = mapaAcentosHex[letra];
    term = term.replace(expressaoRegular, letra);
  }
  return term;
}
```

//Limit text amount
```javascript
LimitCharacters(paragraph: string, limit: number = 100) {
  paragraph = this.RemoveTags(paragraph);
  paragraph =
  paragraph.length > limit
    ? paragraph.substring(0, limit) + "..."
    : paragraph.substring(0, limit);
return paragraph;
}
```

//Remove html tags
```javascript
RemoveTags(html: string) {
  let content = document.createElement("div");
  content.innerHTML = html;
  return content.textContent || content.innerText || "";
}
```

//Convert timestamp
```javascript
ConvertTimestapDate(timestamp: number) {
  var date = new Date(timestamp * 1000);
  return (
    ("0" + date.getDate()).slice(-2) +
    "/" +
    ("0" + (date.getMonth() + 1)).slice(-2) +
    "/" +
    date.getFullYear()
  );
}
```
