## API Report File for "@sussudio/base/common/mime"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

// @public (undocumented)
export function getExtensionForMimeType(mimeType: string): string | undefined;

// @public (undocumented)
export function getMediaMime(path: string): string | undefined;

// @public (undocumented)
export function getMediaOrTextMime(path: string): string | undefined;

// @public (undocumented)
export const Mimes: Readonly<{
    	text: 'text/plain';
    	binary: 'application/octet-stream';
    	unknown: 'application/unknown';
    	markdown: 'text/markdown';
    	latex: 'text/latex';
    	uriList: 'text/uri-list';
}>;

// @public (undocumented)
export function normalizeMimeType(mimeType: string): string;

// @public (undocumented)
export function normalizeMimeType(mimeType: string, strict: true): string | undefined;

// (No @packageDocumentation comment for this package)

```
