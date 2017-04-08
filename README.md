# api documentation for  [imagemin (v5.2.2)](https://github.com/imagemin/imagemin#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-imagemin.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-imagemin) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-imagemin.svg)](https://travis-ci.org/npmdoc/node-npmdoc-imagemin)
#### Minify images

[![NPM](https://nodei.co/npm/imagemin.png?downloads=true)](https://www.npmjs.com/package/imagemin)

[![apidoc](https://npmdoc.github.io/node-npmdoc-imagemin/build/screenCapture.buildNpmdoc.browser.%252Fhome%252Ftravis%252Fbuild%252Fnpmdoc%252Fnode-npmdoc-imagemin%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-imagemin/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-imagemin/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-imagemin/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Kevin Mårtensson",
        "email": "kevinmartensson@gmail.com",
        "url": "github.com/kevva"
    },
    "bugs": {
        "url": "https://github.com/imagemin/imagemin/issues"
    },
    "dependencies": {
        "file-type": "^3.8.0",
        "globby": "^5.0.0",
        "mkdirp": "^0.5.1",
        "pify": "^2.3.0",
        "promise.pipe": "^3.0.0",
        "replace-ext": "0.0.1"
    },
    "description": "Minify images",
    "devDependencies": {
        "ava": "*",
        "del": "^2.2.0",
        "imagemin-jpegtran": "^5.0.0",
        "imagemin-webp": "^4.0.0",
        "is-jpg": "^1.0.0",
        "mkdirp": "^0.5.1",
        "tempfile": "^1.1.1",
        "xo": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "e14a0f357f8810266875eda38634eeb96f6fbd16",
        "tarball": "https://registry.npmjs.org/imagemin/-/imagemin-5.2.2.tgz"
    },
    "engines": {
        "node": ">=4"
    },
    "files": [
        "index.js"
    ],
    "gitHead": "e67e8b9b2f09ab29299331f4606fd1f532f59d59",
    "homepage": "https://github.com/imagemin/imagemin#readme",
    "keywords": [
        "minify",
        "compress",
        "image",
        "images",
        "jpeg",
        "jpg",
        "png",
        "gif",
        "svg"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "kevva",
            "email": "kevinmartensson@gmail.com"
        },
        {
            "name": "shinnn",
            "email": "snnskwtnb@gmail.com"
        },
        {
            "name": "sindresorhus",
            "email": "sindresorhus@gmail.com"
        }
    ],
    "name": "imagemin",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/imagemin/imagemin.git"
    },
    "scripts": {
        "test": "xo && ava"
    },
    "version": "5.2.2"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module imagemin](#apidoc.module.imagemin)
1.  [function <span class="apidocSignatureSpan">imagemin.</span>buffer (input, opts)](#apidoc.element.imagemin.buffer)



# <a name="apidoc.module.imagemin"></a>[module imagemin](#apidoc.module.imagemin)

#### <a name="apidoc.element.imagemin.buffer"></a>[function <span class="apidocSignatureSpan">imagemin.</span>buffer (input, opts)](#apidoc.element.imagemin.buffer)
- description and source-code
```javascript
(input, opts) => {
	if (!Buffer.isBuffer(input)) {
		return Promise.reject(new TypeError('Expected a buffer'));
	}

	opts = Object.assign({plugins: []}, opts);
	opts.plugins = opts.use || opts.plugins;

	const pipe = opts.plugins.length > 0 ? promisePipe(opts.plugins)(input) : Promise.resolve(input);

	return pipe.then(buf => buf.length < input.length ? buf : input);
}
```
- example usage
```shell
...

##### plugins

Type: 'array'

Array of [plugins](https://www.npmjs.com/browse/keyword/imageminplugin) to use.

### imagemin.buffer(buffer, [options])

Returns a promise for a buffer.

#### buffer

Type: 'buffer'
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
