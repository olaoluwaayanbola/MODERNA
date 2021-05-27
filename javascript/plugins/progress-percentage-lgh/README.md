# jquery-progress-lgh
jquery-progress-lgh is a progress component depend on jquery

## Basic Usages
```
<div class="progress">
  <div class="progress-bar progress-bar-striped" role="progressbar" style="width: 0;" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100" id="demo"></div>
</div>
<script type="text/javascript" src="jquery.min.js"></script>
<script type="text/javascript" src="jquery-progress-lgh.min.js"></script>
<script type="text/javascript">
  // step-1
  const progress = new Progress({
              get: function () {
                // get the percentage callback function
                // in this function, you need to get the real-time percentage through the interface, websocket or other channels, 
                // and then update the progress component
                progress.update(percentage);
              },
              set: function (percentage) {
                // set the percentage callback function
                // in this function, you need to render the view with the percentage in the parameter.
                $('#demo').css('width', percentage+'%').text(percentage+'%');
              }
            });
  // step2 start
  progress.start();
</script>
```

and you can use some methods

```
progress.start(); // start the progress component.
progress.update(percentage, jump); // update the real-time percentage. if jump is true, update the real-time percentage immediately without debounce.
progress.finish(); // update the percentage to 100% and stop run.
progress.reset(); // update the percentage to 0% and stop run.
```

## License
MIT License

## Contact
1947501227@qq.com