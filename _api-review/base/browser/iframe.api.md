## API Report File for "@sussudio/base/browser/iframe"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

// @public (undocumented)
export class IframeUtils {
    	static getPositionOfChildWindowRelativeToAncestorWindow(
    		childWindow: Window,
    		ancestorWindow: Window | null,
    	): {
        		top: number;
        		left: number;
        	};
    	static getSameOriginWindowChain(): IWindowChainElement[];
    	static hasDifferentOriginAncestor(): boolean;
}

// @public
export interface IWindowChainElement {
    	iframeElement: Element | null;
    	window: Window;
}

// (No @packageDocumentation comment for this package)

```
