bem-precompiled
---------------

This project contains `i-bem.js` with basic dependencies as well as basic BEMHTML templates precompiled.

Please remember that this project is for learn purposes only!
Production compilation with the help of `bem-tools` gives much better optimized code.

Here's an example of how you can add custom BEMHTML templates and declare client-side JavaScript with the help of `i-bem` in `scripts.js`:

````javascript
function extendTemplates(apply, applyNext, applyCtx, block, elem, tag, attrs, cls, js, jsAttr, bem, mix, content) {
    /* add you BEMHTML templates here  */
    block('test')(
        tag()('my-test-tag'),
        js()(true)
    );
}

BEM.DOM.decl('b-page', {
    onSetMod: {
        js: {
            inited: function() {
                BEM.DOM.append(this.domElem, BEMHTML.apply({ block: 'test' }));
            }
        }
    }
});

BEM.DOM.decl('test', {
    onSetMod: {
        js: {
            inited: function() {
                console.log('inited');
            }
        }
    }
});

/* add the rest of your client-side js here */
````
