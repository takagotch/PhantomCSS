### phantomCSS
---
https://github.com/HuddleEng/PhantomCSS

```css
casper.
  start( url ).
  then(function(){
    casper.click('button#open-dialog');
    phantomcss.screenshot('#the-dialog', 'a screenshot of my dialog');
  });
  
phantomcss.init({
  captureWaitEnabled: true,
    libraryRoot: './modules/PhantomCSS',
    screenshotRoot: './screenshots',
    failedComparisonRoot: './failures',
    cleanupComparisonImages: true,
    casper: specific_instance_of_casper,
    comparisonResultRoot: './results',
    additeratorImage: false,
    addLabelFailedImage: false,
    mismatchTolerance: 0.05,
    onFail: function(test){ console.log(test.filename, test.mismatch); },
    onPass: function(test){ console.log(test.filename); },
    onNewImage: function(){ console.log(test.filename); },
    onTimeout: function(){ console.log(test.filename); },
    onComplete: function(allTests, noOfFails, onOfErrors){
      allTests.forEach(function(test){
        if(test.fail){
          console.log(test.filename, test.mismatch);
        }
      });
    },
    onCaptureFail: function(ex, target){
      console.log('Capture of' + target + ' failed due to ' + ex.message); },
    fileNameGetter: function(root, filename){
      var name = root+''+filename;
      if(fs.isFile(name+'.png')){
        return name+'.diff.png'
      } else {
        return name+'.png';
      }
    },
    prefixCount: true,
    outputSettings{
      errorColor: {
        red: 255,
        green: 255,
        blue: 0
      },
      errorType: 'movement',
      transparency: 0.3
    },
    rebase: casper.cli.get("rebase"),
    failOnCaptureError: false
});
phantomcss.turnOffAnimations();

phantomcss.init({
  outputSettings: {
    errorColor: {
      red: 255,
      green: 255,
      blue: 0
    },
    errorType: 'movement',
    transparency: 0.3
  }
});

phantomcss.compareAll('exclude.test');
//phantomcss.compareMatched('include.test', 'exclude.test');
//phantomcss.compareMatched( new RegExp('include.test'), new RegExp('exclude.test'))
//phantomcss.compareSession();
//phantomcss.compareExplicit(['/dialog.diff.png', '/header.diff.png']);
//phantomcss.getCreateDiffFiles();
//phantomcss.compareFiles(baseFile, diffFile);
//phantomcss.waitForTests();

var delay, hideElementSelector;
phantomcss.screenshot("#feedback-form", delay, hideElementsSelector, "Responsive Feedback Form");
phantomcss.screenshot("#feedback-form", "Responsive Feedback Form");

phantomcss.screenshot("#sidebar li:nth-child(3) > div form");

phantomcss.screenshot("#feedback-form");

phantomcsss.screenshot("#feedback-form", undefined, 'input[type=file]');
```

```sh
casperjs test demo/testsuite.js --engine=slimerjs
```

```js
var delay = 10;
var hideElements = 'input[type=file]';
var screenshotName = 'the_dialog'
phantomcss.screenshot( "#CSS .selector", screenshotName );
// phantomcss.screenshot({
//  'Screenshot 1 File name': {selector: '.screenshot1', ignore: '.selector'},
//  'Screenshot 2 File name': '#screenshot2'
// });
//phantomcss.screenshot( "#CSS .selector" );
//phantomcss.screenshot( "#CSS .selector", delay, hideElements, screenshotName);
//phatomcss.screenshot({
//  top: 100,
//  left: 100,
//  width: 500,
//  height: 400
// }, screenshotName);

```

