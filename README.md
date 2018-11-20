### phantomCSS
---
https://github.com/HuddleEng/PhantomCSS

```
casper.
  start( url ).
  then(function(){
    casper.click('button#open-dialog');
    phantomcss.screenshot('#the-dialog', 'a screenshot of my dialog');
  });
  
  
```

```sh
casperjs test demo/testsuite.js --engine=slimerjs
```

```
```

