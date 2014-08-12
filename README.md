to investigate why zlib.createDeflate seems to be very slow if you don't let the underlying buffer drain by watching the return value of write.  The tests will pass if you set the fileSize to 50KB but tests will start churning like crazy if you set it to something like 200KB

```
npm install
cd tests
mocha tests.js
```

To see how it works with draining enabled modify tests.js and set allowDrain = true;