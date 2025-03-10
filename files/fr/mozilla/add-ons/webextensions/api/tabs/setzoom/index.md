---
title: tabs.setZoom()
slug: Mozilla/Add-ons/WebExtensions/API/tabs/setZoom
tags:
  - API
  - Add-ons
  - Extensions
  - Method
  - Non-standard
  - Reference
  - WebExtensions
  - setZoom
  - tabs
translation_of: Mozilla/Add-ons/WebExtensions/API/tabs/setZoom
---
{{AddonSidebar()}}

Effectue un zoom sur l'onglet spécifié.

C'est une fonction asynchrone qui renvoie une [`Promise`](/fr/docs/Web/JavaScript/Reference/Objets_globaux/Promise).

## Syntaxe

```js
var zooming = browser.tabs.setZoom(
  tabId,           // optional integer
  zoomFactor       // number
)
```

### Paramètres

- `tabId`{{optional_inline}}
  - : `integer`. L'ID de l'onglet à zoomer. Par défaut à l'onglet actif de la fenêtre en cours.
- `zoomFactor`
  - : `number`. Le nouveau facteur de zoom. Utilisez une valeur de 0 ici pour régler l'onglet à son facteur de zoom par défaut actuel. Sinon, il doit s'agir d'un nombre compris entre 0,3 et 3, en spécifiant un facteur de zoom.

### Valeur retournée

Une [`Promise`](/fr/docs/Web/JavaScript/Reference/Objets_globaux/Promise) cela sera accompli sans arguments après que le facteur de zoom ait été changé. Si l'onglet n'a pas pu être trouvé ou qu'une autre erreur se produit, la promesse sera rejetée avec un message d'erreur.

## Exemples

Set the zoom factor for the current tab to 2:

```js
function onError(error) {
  console.log(`Error: ${error}`);
}

var setting = browser.tabs.setZoom(2);
setting.then(null, onError);
```

Set the zoom factor for the tab whose ID is 16 tab to 0.5:

```js
function onError(error) {
  console.log(`Error: ${error}`);
}

var setting = browser.tabs.setZoom(16, 0.5);
setting.then(null, onError);
```

{{WebExtExamples}}

## Compatibilité du navigateur

{{Compat("webextensions.api.tabs.setZoom")}}

> **Note :**
>
> Cette API est basée sur l’API [`chrome.tabs`](https://developer.chrome.com/extensions/tabs#method-executeScript) de Chromium. Cette documentation est dérivée de [`tabs.json`](https://chromium.googlesource.com/chromium/src/+/master/chrome/common/extensions/api/tabs.json) dans le code de Chromium code.
>
> Les données de compatibilité relatives à Microsoft Edge sont fournies par Microsoft Corporation et incluses ici sous la licence Creative Commons Attribution 3.0 pour les États-Unis.

<div class="hidden"><pre>// Copyright 2015 The Chromium Authors. All rights reserved.
//
// Redistribution and use in source and binary forms, with or without
// modification, are permitted provided that the following conditions are
// met:
//
//    * Redistributions of source code must retain the above copyright
// notice, this list of conditions and the following disclaimer.
//    * Redistributions in binary form must reproduce the above
// copyright notice, this list of conditions and the following disclaimer
// in the documentation and/or other materials provided with the
// distribution.
//    * Neither the name of Google Inc. nor the names of its
// contributors may be used to endorse or promote products derived from
// this software without specific prior written permission.
//
// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
</pre></div>
