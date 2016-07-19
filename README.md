Disk Usage Time Series
======================

```js
var diskseries = require("diskseries"),
    disk = diskseries("/dev/sda1");

setInterval(function() {
    var ma;

    disk.sample();
    ma = disk.series().ma().output().slice(-1).pop();
    console.log("disk sampled; moving average:", ma);
}, 60*1000);
```

Analysis
--------
The value returned by the `.series()` method is a time series built using the
[`timeseries-analysis`](https://www.npmjs.com/package/timeseries-analysis)
package.  Further information on timeseries analysis can be obtained from
those docs.
