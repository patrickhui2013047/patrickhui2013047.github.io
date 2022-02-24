---
layout: post
title: A translator project
---

---

The project is not finished yet, the content here may be change after update

---

I started a translator project recently, which is a modularize program. 
The program included three core module `TextProvider`, `TranslationProvider` and `DisplayProvider`. 
`TextProvider` supply the source text; `TranslationProvider`supply the translation service and `DisplayProvider` supply the output channel.

All the providers must implement their own interface `ITextProvider`, `ITranslationProvider` and `IDisplayProvider`. 
To prevent conflict, a single provider class can only implement one kind of provider.
All the provider follow the same naming rule `[NameOfService|NameOfProvider][Text|Translation|Display]Provider`, like `ClipboardTextProvider`, `DummyTranslationProvider` and `ConsoleDisplayProvider`.
Since the providers' class name are used as their unique indenifer, all the provider class should not share the same name.

## 24/02/2022 Progress log
 - [x] Core structure
 - [x] Console UI for testing only
 - [x] ClipboardTextProvider
 - [x] DummyTranslationProvider
 - [x] ConsoleDisplayProvider
 - [x]