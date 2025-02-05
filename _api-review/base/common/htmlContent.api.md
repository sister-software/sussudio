## API Report File for "@sussudio/base/common/htmlContent"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

// @public (undocumented)
export function escapeDoubleQuotes(input: string): string;

// @public (undocumented)
export function escapeMarkdownSyntaxTokens(text: string): string;

// @public (undocumented)
export interface IMarkdownString {
    	// (undocumented)
    readonly baseUri?: UriComponents;
    	// (undocumented)
    readonly isTrusted?: boolean | MarkdownStringTrustedOptions;
    	// (undocumented)
    readonly supportHtml?: boolean;
    	// (undocumented)
    readonly supportThemeIcons?: boolean;
    	// (undocumented)
    uris?: {
        		[href: string]: UriComponents;
        	};
    	// (undocumented)
    readonly value: string;
}

// @public (undocumented)
export function isEmptyMarkdownString(
	oneOrMany: IMarkdownString | IMarkdownString[] | null | undefined,
): boolean;

// @public (undocumented)
export function isMarkdownString(thing: any): thing is IMarkdownString;

// @public (undocumented)
export class MarkdownString implements IMarkdownString {
    	constructor(
    		value?: string,
    		isTrustedOrOptions?:
    			| boolean
    			| {
        					isTrusted?: boolean | MarkdownStringTrustedOptions;
        					supportThemeIcons?: boolean;
        					supportHtml?: boolean;
        			  },
    	);
    	// (undocumented)
    appendCodeblock(langId: string, code: string): MarkdownString;
    	// (undocumented)
    appendLink(target: URI | string, label: string, title?: string): MarkdownString;
    	// (undocumented)
    appendMarkdown(value: string): MarkdownString;
    	// (undocumented)
    appendText(value: string, newlineStyle?: MarkdownStringTextNewlineStyle): MarkdownString;
    	// (undocumented)
    baseUri?: URI;
    	// (undocumented)
    isTrusted?: boolean | MarkdownStringTrustedOptions;
    	// (undocumented)
    supportHtml?: boolean;
    	// (undocumented)
    supportThemeIcons?: boolean;
    	// (undocumented)
    value: string;
}

// @public (undocumented)
export function markdownStringEqual(a: IMarkdownString, b: IMarkdownString): boolean;

// @public (undocumented)
export const enum MarkdownStringTextNewlineStyle {
    	// (undocumented)
    Break = 1,
    	// (undocumented)
    Paragraph = 0,
}

// @public (undocumented)
export interface MarkdownStringTrustedOptions {
    	// (undocumented)
    readonly enabledCommands: readonly string[];
}

// @public (undocumented)
export function parseHrefAndDimensions(href: string): {
    	href: string;
    	dimensions: string[];
};

// @public (undocumented)
export function removeMarkdownEscapes(text: string): string;

// @public
class URI implements UriComponents {
    	// @internal
    protected constructor(
    		scheme: string,
    		authority?: string,
    		path?: string,
    		query?: string,
    		fragment?: string,
    		_strict?: boolean,
    	);
    	// @internal
    protected constructor(components: UriComponents);
    	readonly authority: string;
    	static file(path: string): URI;
    	readonly fragment: string;
    	// (undocumented)
    static from(components: {
        		scheme: string;
        		authority?: string;
        		path?: string;
        		query?: string;
        		fragment?: string;
        	}): URI;
    	get fsPath(): string;
    	// (undocumented)
    static isUri(thing: any): thing is URI;
    	static joinPath(uri: URI, ...pathFragment: string[]): URI;
    	static parse(value: string, _strict?: boolean): URI;
    	readonly path: string;
    	readonly query: string;
    	// (undocumented)
    static revive(data: UriComponents | URI): URI;
    	// (undocumented)
    static revive(data: UriComponents | URI | undefined): URI | undefined;
    	// (undocumented)
    static revive(data: UriComponents | URI | null): URI | null;
    	// (undocumented)
    static revive(data: UriComponents | URI | undefined | null): URI | undefined | null;
    	readonly scheme: string;
    	// (undocumented)
    toJSON(): UriComponents;
    	toString(skipEncoding?: boolean): string;
    	// (undocumented)
    with(change: {
        		scheme?: string;
        		authority?: string | null;
        		path?: string | null;
        		query?: string | null;
        		fragment?: string | null;
        	}): URI;
}

// @public (undocumented)
interface UriComponents {
    	// (undocumented)
    authority: string;
    	// (undocumented)
    fragment: string;
    	// (undocumented)
    path: string;
    	// (undocumented)
    query: string;
    	// (undocumented)
    scheme: string;
}

// (No @packageDocumentation comment for this package)

```
