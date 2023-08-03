JavaScript library un7z unzip unrar
====
> zip 7z only support english name.

```javascript
    FetchItem = async e=>new Uint8Array(await (await fetch(e)).arrayBuffer());
    w=new Worker('extractor.js');
    w.onmessage = e=>console.log(e.data);
    w.postMessage({
        //DB_NAME:T.DB_NAME,
        //DB_TABLE:T.LibStore,
        //DB_FILE:'script-extractor.wasm',
        filename:'xxx.abc',
        wasmBinary: await FetchItem('extractor.wasm'),
        contents:await FetchItem('../psx-wasm.7z')
    });
    //or common.js
    k=await T.FetchItem({
        url:T.JSpath+'lib/extractor.zip?900',
        unbuf:I.L(10),
        libjs:!0,
        unpack:!0
    });
    w=new Worker(F.URL(k));
    w.onmessage = e=>console.log(e.data);
    w.postMessage({
        DB_NAME:T.DB_NAME,
        DB_TABLE:T.LibStore,
        DB_FILE:'script-extractor.wasm',
        filename:'xxx.abc',
        contents:await T.FetchItem({url:'../psx-wasm.7z',})
    });
```