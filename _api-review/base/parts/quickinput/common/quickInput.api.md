## API Report File for "@sussudio/base/parts/quickinput/common/quickInput"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

// @public
class DisposableStore implements IDisposable {
    	constructor();
    	add<T extends IDisposable>(o: T): T;
    	clear(): void;
    	// (undocumented)
    static DISABLE_DISPOSED_WARNING: boolean;
    	dispose(): void;
    	// (undocumented)
    get isDisposed(): boolean;
    	}

// @public
interface Event_2<T> {
    	// (undocumented)
    (listener: (e: T) => any, thisArgs?: any, disposables?: IDisposable[] | DisposableStore): IDisposable;
}

// @public (undocumented)
namespace Event_2 {
    	const // (undocumented)
    None: Event_2<any>;
    	function accumulate<T>(event: Event_2<T>, delay?: number, disposable?: DisposableStore): Event_2<T[]>;
    	function any<T>(...events: Event_2<T>[]): Event_2<T>;
    	// (undocumented)
    function any(...events: Event_2<any>[]): Event_2<void>;
    	function buffer<T>(event: Event_2<T>, flushAfterTimeout?: boolean, _buffer?: T[]): Event_2<T>;
    	// (undocumented)
    function chain<T>(event: Event_2<T>): IChainableEvent<T>;
    	function debounce<T>(
    		event: Event_2<T>,
    		merge: (last: T | undefined, event: T) => T,
    		delay?: number,
    		leading?: boolean,
    		leakWarningThreshold?: number,
    		disposable?: DisposableStore,
    	): Event_2<T>;
    	function debounce<I, O>(
    		event: Event_2<I>,
    		merge: (last: O | undefined, event: I) => O,
    		delay?: number,
    		leading?: boolean,
    		leakWarningThreshold?: number,
    		disposable?: DisposableStore,
    	): Event_2<O>;
    	function defer(event: Event_2<unknown>, disposable?: DisposableStore): Event_2<void>;
    	// (undocumented)
    interface DOMEventEmitter {
        		// (undocumented)
        addEventListener(event: string | symbol, listener: Function): void;
        		// (undocumented)
        removeEventListener(event: string | symbol, listener: Function): void;
        	}
    	function filter<T, U>(event: Event_2<T | U>, filter: (e: T | U) => e is T, disposable?: DisposableStore): Event_2<T>;
    	// (undocumented)
    function filter<T>(event: Event_2<T>, filter: (e: T) => boolean, disposable?: DisposableStore): Event_2<T>;
    	// (undocumented)
    function filter<T, R>(event: Event_2<T | R>, filter: (e: T | R) => e is R, disposable?: DisposableStore): Event_2<R>;
    	function forEach<I>(event: Event_2<I>, each: (i: I) => void, disposable?: DisposableStore): Event_2<I>;
    	// (undocumented)
    function fromDOMEventEmitter<T>(emitter: DOMEventEmitter, eventName: string, map?: (...args: any[]) => T): Event_2<T>;
    	// (undocumented)
    function fromNodeEventEmitter<T>(emitter: NodeEventEmitter, eventName: string, map?: (...args: any[]) => T): Event_2<T>;
    	// (undocumented)
    function fromObservable<T>(obs: IObservable<T, any>, store?: DisposableStore): Event_2<T>;
    	// (undocumented)
    interface IChainableEvent<T> extends IDisposable {
        		// (undocumented)
        debounce(
        			merge: (last: T | undefined, event: T) => T,
        			delay?: number,
        			leading?: boolean,
        			leakWarningThreshold?: number,
        		): IChainableEvent<T>;
        		// (undocumented)
        debounce<R>(
        			merge: (last: R | undefined, event: T) => R,
        			delay?: number,
        			leading?: boolean,
        			leakWarningThreshold?: number,
        		): IChainableEvent<R>;
        		// (undocumented)
        event: Event_2<T>;
        		// (undocumented)
        filter(fn: (e: T) => boolean): IChainableEvent<T>;
        		// (undocumented)
        filter<R>(fn: (e: T | R) => e is R): IChainableEvent<R>;
        		// (undocumented)
        forEach(fn: (i: T) => void): IChainableEvent<T>;
        		// (undocumented)
        latch(): IChainableEvent<T>;
        		// (undocumented)
        map<O>(fn: (i: T) => O): IChainableEvent<O>;
        		// (undocumented)
        on(listener: (e: T) => any, thisArgs?: any, disposables?: IDisposable[] | DisposableStore): IDisposable;
        		// (undocumented)
        once(listener: (e: T) => any, thisArgs?: any, disposables?: IDisposable[]): IDisposable;
        		// (undocumented)
        reduce<R>(merge: (last: R | undefined, event: T) => R, initial?: R): IChainableEvent<R>;
        	}
    	function latch<T>(event: Event_2<T>, equals?: (a: T, b: T) => boolean, disposable?: DisposableStore): Event_2<T>;
    	function map<I, O>(event: Event_2<I>, map: (i: I) => O, disposable?: DisposableStore): Event_2<O>;
    	// (undocumented)
    interface NodeEventEmitter {
        		// (undocumented)
        on(event: string | symbol, listener: Function): unknown;
        		// (undocumented)
        removeListener(event: string | symbol, listener: Function): unknown;
        	}
    	function once<T>(event: Event_2<T>): Event_2<T>;
    	function reduce<I, O>(
    		event: Event_2<I>,
    		merge: (last: O | undefined, event: I) => O,
    		initial?: O,
    		disposable?: DisposableStore,
    	): Event_2<O>;
    	// (undocumented)
    function runAndSubscribe<T>(event: Event_2<T>, handler: (e: T | undefined) => any): IDisposable;
    	// (undocumented)
    function runAndSubscribeWithStore<T>(
    		event: Event_2<T>,
    		handler: (e: T | undefined, disposableStore: DisposableStore) => any,
    	): IDisposable;
    	function signal<T>(event: Event_2<T>): Event_2<void>;
    	function split<T, U>(
    		event: Event_2<T | U>,
    		isT: (e: T | U) => e is T,
    		disposable?: DisposableStore,
    	): [Event_2<T>, Event_2<U>];
    	// (undocumented)
    function toPromise<T>(event: Event_2<T>): Promise<T>;
}

// @public
interface IDisposable {
    	// (undocumented)
    dispose(): void;
}

// @public (undocumented)
export interface IInputBox extends IQuickInput {
    	buttons: ReadonlyArray<IQuickInputButton>;
    	readonly onDidAccept: Event_2<void>;
    	readonly onDidChangeValue: Event_2<string>;
    	readonly onDidTriggerButton: Event_2<IQuickInputButton>;
    	password: boolean;
    	placeholder: string | undefined;
    	prompt: string | undefined;
    	severity: Severity;
    	validationMessage: string | undefined;
    	value: string;
    	valueSelection: Readonly<[number, number]> | undefined;
}

// @public (undocumented)
export interface IInputOptions {
    	ignoreFocusLost?: boolean;
    	password?: boolean;
    	placeHolder?: string;
    	prompt?: string;
    	title?: string;
    	validateInput?: (input: string) => Promise<
    		| string
    		| null
    		| undefined
    		| {
        				content: string;
        				severity: Severity;
        		  }
    	>;
    	value?: string;
    	valueSelection?: readonly [number, number];
}

// @public (undocumented)
interface IItemAccessor<T> {
    	getItemDescription(item: T): string | undefined;
    	getItemLabel(item: T): string | undefined;
    	getItemPath(file: T): string | undefined;
}

// @public (undocumented)
export interface IKeyMods {
    	// (undocumented)
    readonly alt: boolean;
    	// (undocumented)
    readonly ctrlCmd: boolean;
}

// @public (undocumented)
interface IMatch {
    	// (undocumented)
    end: number;
    	// (undocumented)
    start: number;
}

// @public (undocumented)
interface IObservable<T, _TChange = void> {
    	addObserver(observer: IObserver): void;
    	// (undocumented)
    readonly debugName: string;
    	get(): T;
    	// (undocumented)
    map<TNew>(fn: (value: T) => TNew): IObservable<TNew>;
    	read(reader: IReader): T;
    	// (undocumented)
    removeObserver(observer: IObserver): void;
    	// (undocumented)
    readonly TChange: _TChange;
}

// @public (undocumented)
interface IObserver {
    	beginUpdate<T>(observable: IObservable<T>): void;
    	endUpdate<T>(observable: IObservable<T>): void;
    	handleChange<T, TChange>(observable: IObservable<T, TChange>, change: TChange): void;
}

// @public (undocumented)
export interface IPickOptions<T extends IQuickPickItem> {
    	activeItem?: Promise<T> | T;
    	autoFocusOnList?: boolean;
    	canPickMany?: boolean;
    	contextKey?: string;
    	hideInput?: boolean;
    	ignoreFocusLost?: boolean;
    	matchOnDescription?: boolean;
    	matchOnDetail?: boolean;
    	matchOnLabel?: boolean;
    	// (undocumented)
    onDidFocus?: (entry: T) => void;
    	// (undocumented)
    onDidTriggerItemButton?: (context: IQuickPickItemButtonContext<T>) => void;
    	// (undocumented)
    onDidTriggerSeparatorButton?: (context: IQuickPickSeparatorButtonEvent) => void;
    	// (undocumented)
    onKeyMods?: (keyMods: IKeyMods) => void;
    	placeHolder?: string;
    	quickNavigate?: IQuickNavigateConfiguration;
    	title?: string;
}

// @public (undocumented)
export interface IQuickInput extends IDisposable {
    	// (undocumented)
    busy: boolean;
    	// (undocumented)
    contextKey: string | undefined;
    	// (undocumented)
    description: string | undefined;
    	// (undocumented)
    enabled: boolean;
    	// (undocumented)
    hide(): void;
    	// (undocumented)
    ignoreFocusOut: boolean;
    	// (undocumented)
    readonly onDidHide: Event_2<IQuickInputHideEvent>;
    	// (undocumented)
    readonly onDispose: Event_2<void>;
    	// (undocumented)
    show(): void;
    	// (undocumented)
    step: number | undefined;
    	// (undocumented)
    title: string | undefined;
    	// (undocumented)
    totalSteps: number | undefined;
}

// @public (undocumented)
export interface IQuickInputButton {
    	alwaysVisible?: boolean;
    	iconClass?: string;
    	iconPath?: {
        		dark: URI;
        		light?: URI;
        	};
    	// (undocumented)
    tooltip?: string;
}

// @public (undocumented)
export interface IQuickInputHideEvent {
    	// (undocumented)
    reason: QuickInputHideReason;
}

// @public (undocumented)
export interface IQuickInputToggle {
    	// (undocumented)
    onChange: Event_2<boolean>;
}

// @public (undocumented)
export interface IQuickNavigateConfiguration {
    	// (undocumented)
    keybindings: readonly ResolvedKeybinding[];
}

// @public (undocumented)
export interface IQuickPick<T extends IQuickPickItem> extends IQuickInput {
    	// (undocumented)
    activeItems: ReadonlyArray<T>;
    	// (undocumented)
    ariaLabel: string | undefined;
    	// (undocumented)
    autoFocusOnList: boolean;
    	// (undocumented)
    buttons: ReadonlyArray<IQuickInputButton>;
    	canAcceptInBackground: boolean;
    	// (undocumented)
    canSelectMany: boolean;
    	// (undocumented)
    customButton: boolean;
    	// (undocumented)
    customHover: string | undefined;
    	// (undocumented)
    customLabel: string | undefined;
    	filterValue: (value: string) => string;
    	// (undocumented)
    focusOnInput(): void;
    	// (undocumented)
    hideCheckAll: boolean;
    	hideInput: boolean;
    	// (undocumented)
    inputHasFocus(): boolean;
    	itemActivation: ItemActivation;
    	// (undocumented)
    items: ReadonlyArray<T | IQuickPickSeparator>;
    	// (undocumented)
    keepScrollPosition: boolean;
    	// (undocumented)
    readonly keyMods: IKeyMods;
    	// (undocumented)
    matchOnDescription: boolean;
    	// (undocumented)
    matchOnDetail: boolean;
    	// (undocumented)
    matchOnLabel: boolean;
    	matchOnLabelMode: 'fuzzy' | 'contiguous';
    	// (undocumented)
    ok: boolean | 'default';
    	// (undocumented)
    readonly onDidAccept: Event_2<IQuickPickDidAcceptEvent>;
    	// (undocumented)
    readonly onDidChangeActive: Event_2<T[]>;
    	// (undocumented)
    readonly onDidChangeSelection: Event_2<T[]>;
    	// (undocumented)
    readonly onDidChangeValue: Event_2<string>;
    	// (undocumented)
    readonly onDidCustom: Event_2<void>;
    	// (undocumented)
    readonly onDidTriggerButton: Event_2<IQuickInputButton>;
    	// (undocumented)
    readonly onDidTriggerItemButton: Event_2<IQuickPickItemButtonEvent<T>>;
    	// (undocumented)
    readonly onDidTriggerSeparatorButton: Event_2<IQuickPickSeparatorButtonEvent>;
    	// (undocumented)
    readonly onWillAccept: Event_2<IQuickPickWillAcceptEvent>;
    	// (undocumented)
    placeholder: string | undefined;
    	// (undocumented)
    quickNavigate: IQuickNavigateConfiguration | undefined;
    	// (undocumented)
    scrollTop: number;
    	// (undocumented)
    selectedItems: ReadonlyArray<T>;
    	// (undocumented)
    sortByLabel: boolean;
    	toggles: IQuickInputToggle[] | undefined;
    	// (undocumented)
    validationMessage: string | undefined;
    	// (undocumented)
    value: string;
    	// (undocumented)
    valueSelection: Readonly<[number, number]> | undefined;
}

// @public (undocumented)
export interface IQuickPickDidAcceptEvent {
    	inBackground: boolean;
}

// @public (undocumented)
export interface IQuickPickItem {
    	// (undocumented)
    alwaysShow?: boolean;
    	// (undocumented)
    ariaLabel?: string;
    	// (undocumented)
    buttons?: readonly IQuickInputButton[];
    	// (undocumented)
    description?: string;
    	// (undocumented)
    detail?: string;
    	// (undocumented)
    highlights?: IQuickPickItemHighlights;
    	// (undocumented)
    iconClasses?: readonly string[];
    	// (undocumented)
    id?: string;
    	// (undocumented)
    italic?: boolean;
    	keybinding?: ResolvedKeybinding;
    	// (undocumented)
    label: string;
    	// (undocumented)
    meta?: string;
    	// (undocumented)
    picked?: boolean;
    	// (undocumented)
    strikethrough?: boolean;
    	// (undocumented)
    type?: 'item';
}

// @public (undocumented)
export interface IQuickPickItemButtonContext<T extends IQuickPickItem> extends IQuickPickItemButtonEvent<T> {
    	// (undocumented)
    removeItem(): void;
}

// @public (undocumented)
export interface IQuickPickItemButtonEvent<T extends IQuickPickItem> {
    	// (undocumented)
    button: IQuickInputButton;
    	// (undocumented)
    item: T;
}

// @public (undocumented)
export interface IQuickPickItemHighlights {
    	// (undocumented)
    description?: IMatch[];
    	// (undocumented)
    detail?: IMatch[];
    	// (undocumented)
    label?: IMatch[];
}

// @public (undocumented)
export type IQuickPickItemWithResource = IQuickPickItem & {
    	resource?: URI;
};

// @public (undocumented)
export interface IQuickPickSeparator {
    	// (undocumented)
    ariaLabel?: string;
    	// (undocumented)
    buttons?: readonly IQuickInputButton[];
    	// (undocumented)
    id?: string;
    	// (undocumented)
    label?: string;
    	// (undocumented)
    type: 'separator';
}

// @public (undocumented)
export interface IQuickPickSeparatorButtonEvent {
    	// (undocumented)
    button: IQuickInputButton;
    	// (undocumented)
    separator: IQuickPickSeparator;
}

// @public (undocumented)
export interface IQuickPickWillAcceptEvent {
    	veto(): void;
}

// @public (undocumented)
interface IReader {
    	subscribeTo<T>(observable: IObservable<T, any>): void;
}

// @public (undocumented)
export enum ItemActivation {
    	// (undocumented)
    FIRST = 1,
    	// (undocumented)
    LAST = 3,
    	// (undocumented)
    NONE = 0,
    	// (undocumented)
    SECOND = 2,
}

// @public (undocumented)
export const NO_KEY_MODS: IKeyMods;

// @public (undocumented)
export enum QuickInputHideReason {
    	Blur = 1,
    	Gesture = 2,
    	Other = 3,
}

// @public (undocumented)
export type QuickPickInput<T = IQuickPickItem> = T | IQuickPickSeparator;

// @public (undocumented)
export type QuickPickItem = IQuickPickSeparator | IQuickPickItem;

// @public (undocumented)
export class QuickPickItemScorerAccessor implements IItemAccessor<IQuickPickItemWithResource> {
    	constructor(
    		options?:
    			| {
        					skipDescription?: boolean | undefined;
        					skipPath?: boolean | undefined;
        			  }
    			| undefined,
    	);
    	// (undocumented)
    getItemDescription(entry: IQuickPickItemWithResource): string | undefined;
    	// (undocumented)
    getItemLabel(entry: IQuickPickItemWithResource): string;
    	// (undocumented)
    getItemPath(entry: IQuickPickItemWithResource): string | undefined;
    	}

// @public (undocumented)
export const quickPickItemScorerAccessor: QuickPickItemScorerAccessor;

// @public (undocumented)
class ResolvedChord {
    	constructor(
    		ctrlKey: boolean,
    		shiftKey: boolean,
    		altKey: boolean,
    		metaKey: boolean,
    		keyLabel: string | null,
    		keyAriaLabel: string | null,
    	);
    	// (undocumented)
    readonly altKey: boolean;
    	// (undocumented)
    readonly ctrlKey: boolean;
    	// (undocumented)
    readonly keyAriaLabel: string | null;
    	// (undocumented)
    readonly keyLabel: string | null;
    	// (undocumented)
    readonly metaKey: boolean;
    	// (undocumented)
    readonly shiftKey: boolean;
}

// @public
abstract class ResolvedKeybinding {
    	abstract getAriaLabel(): string | null;
    	abstract getChords(): ResolvedChord[];
    	abstract getDispatchChords(): (string | null)[];
    	abstract getElectronAccelerator(): string | null;
    	abstract getLabel(): string | null;
    	abstract getSingleModifierDispatchChords(): (SingleModifierChord | null)[];
    	abstract getUserSettingsLabel(): string | null;
    	abstract hasMultipleChords(): boolean;
    	abstract isWYSIWYG(): boolean;
}

// @public (undocumented)
enum Severity {
    	// (undocumented)
    Error = 3,
    	// (undocumented)
    Ignore = 0,
    	// (undocumented)
    Info = 1,
    	// (undocumented)
    Warning = 2,
}

// @public (undocumented)
namespace Severity {
    	function fromValue(value: string): Severity;
    	// (undocumented)
    function toString(severity: Severity): string;
}

// @public (undocumented)
type SingleModifierChord = 'ctrl' | 'shift' | 'alt' | 'meta';

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
