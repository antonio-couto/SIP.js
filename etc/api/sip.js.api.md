## API Report File for "sip.js"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { EventEmitter } from 'events';

// @public
export interface BodyAndContentType {
    body: string;
    contentType: string;
}

// @public
export class Byer {
    constructor(session: Session, options?: ByerOptions);
    // Warning: (ae-forgotten-export) The symbol "OutgoingByeRequest" needs to be exported by the entry point index.d.ts
    bye(options?: ByerByeOptions): Promise<OutgoingByeRequest>;
    get session(): Session;
    }

// @public
export interface ByerByeOptions {
    // Warning: (ae-forgotten-export) The symbol "OutgoingRequestDelegate" needs to be exported by the entry point index.d.ts
    requestDelegate?: OutgoingRequestDelegate;
    // Warning: (ae-forgotten-export) The symbol "RequestOptions" needs to be exported by the entry point index.d.ts
    requestOptions?: RequestOptions;
}

// @public
export interface ByerOptions {
}

// Warning: (ae-forgotten-export) The symbol "Exception" needs to be exported by the entry point index.d.ts
//
// @public
export class ContentTypeUnsupportedError extends Exception {
    constructor(message?: string);
}

// @public
export interface Emitter<T> {
    addListener(listener: (data: T) => void, options?: {
        once?: boolean;
    }): void;
    // @deprecated
    off(listener: (data: T) => void): void;
    // @deprecated
    on(listener: (data: T) => void): void;
    // @deprecated
    once(listener: (data: T) => void): void;
    removeListener(listener: (data: T) => void): void;
}

// @public
export class Info {
    // Warning: (ae-forgotten-export) The symbol "IncomingInfoRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    constructor(incomingInfoRequest: IncomingInfoRequest);
    // Warning: (ae-forgotten-export) The symbol "ResponseOptions" needs to be exported by the entry point index.d.ts
    accept(options?: ResponseOptions): Promise<void>;
    reject(options?: ResponseOptions): Promise<void>;
    // Warning: (ae-forgotten-export) The symbol "IncomingRequestMessage" needs to be exported by the entry point index.d.ts
    get request(): IncomingRequestMessage;
}

// @public
export class Infoer {
    constructor(session: Session, options?: InfoerOptions);
    // Warning: (ae-forgotten-export) The symbol "OutgoingInfoRequest" needs to be exported by the entry point index.d.ts
    info(options?: InfoerInfoOptions): Promise<OutgoingInfoRequest>;
    get session(): Session;
    }

// @public
export interface InfoerInfoOptions {
    requestDelegate?: OutgoingRequestDelegate;
    requestOptions?: RequestOptions;
}

// @public
export interface InfoerOptions {
}

// @public
export class Invitation extends Session {
    // Warning: (ae-forgotten-export) The symbol "IncomingInviteRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    constructor(userAgent: UserAgent, incomingInviteRequest: IncomingInviteRequest);
    accept(options?: InvitationAcceptOptions): Promise<void>;
    // @internal
    get autoSendAnInitialProvisionalResponse(): boolean;
    get body(): string | undefined;
    dispose(): Promise<void>;
    // @internal (undocumented)
    protected _id: string;
    // Warning: (ae-forgotten-export) The symbol "NameAddrHeader" needs to be exported by the entry point index.d.ts
    get localIdentity(): NameAddrHeader;
    // Warning: (ae-forgotten-export) The symbol "Logger" needs to be exported by the entry point index.d.ts
    protected logger: Logger;
    // @internal
    _onCancel(message: IncomingRequestMessage): void;
    progress(options?: InvitationProgressOptions): Promise<void>;
    reject(options?: InvitationRejectOptions): Promise<void>;
    get remoteIdentity(): NameAddrHeader;
    get request(): IncomingRequestMessage;
    }

// @public
export interface InvitationAcceptOptions {
    sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
}

// @public
export interface InvitationProgressOptions {
    body?: string | {
        body: string;
        contentType: string;
    };
    extraHeaders?: Array<string>;
    reasonPhrase?: string;
    rel100?: boolean;
    sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
    statusCode?: number;
}

// @public
export interface InvitationRejectOptions {
    body?: string | {
        body: string;
        contentType: string;
    };
    extraHeaders?: Array<string>;
    reasonPhrase?: string;
    statusCode?: number;
}

// @public
export class Inviter extends Session {
    // Warning: (ae-forgotten-export) The symbol "URI" needs to be exported by the entry point index.d.ts
    constructor(userAgent: UserAgent, targetURI: URI, options?: InviterOptions);
    get body(): BodyAndContentType | undefined;
    cancel(options?: InviterCancelOptions): Promise<void>;
    dispose(): Promise<void>;
    // @internal (undocumented)
    protected _id: string;
    // Warning: (ae-forgotten-export) The symbol "OutgoingInviteRequest" needs to be exported by the entry point index.d.ts
    invite(options?: InviterInviteOptions): Promise<OutgoingInviteRequest>;
    get localIdentity(): NameAddrHeader;
    protected logger: Logger;
    // @internal
    _referred: Session | undefined;
    get remoteIdentity(): NameAddrHeader;
    // Warning: (ae-forgotten-export) The symbol "OutgoingRequestMessage" needs to be exported by the entry point index.d.ts
    get request(): OutgoingRequestMessage;
    }

// @public
export interface InviterCancelOptions {
    // (undocumented)
    extraHeaders?: Array<string>;
    // (undocumented)
    reasonPhrase?: string;
    // (undocumented)
    statusCode?: number;
}

// @public
export interface InviterInviteOptions {
    requestDelegate?: OutgoingRequestDelegate;
    requestOptions?: RequestOptions;
    // (undocumented)
    sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    // (undocumented)
    sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
    withoutSdp?: boolean;
}

// @public
export interface InviterOptions extends SessionOptions {
    anonymous?: boolean;
    earlyMedia?: boolean;
    extraHeaders?: Array<string>;
    inviteWithoutSdp?: boolean;
    // @deprecated (undocumented)
    params?: {
        fromDisplayName?: string;
        fromTag?: string;
        fromUri?: string | URI;
        toDisplayName?: string;
        toUri?: string | URI;
    };
    // @deprecated (undocumented)
    renderbody?: string;
    // @deprecated (undocumented)
    rendertype?: string;
    sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
}

// @public
export type LogConnector = (level: LogLevel, category: string, label: string | undefined, content: string) => void;

// @public
export type LogLevel = "debug" | "log" | "warn" | "error";

// @internal
export function _makeEmitter<T>(eventEmitter: EventEmitter, eventName?: string): Emitter<T>;

// @public
export class Message {
    // Warning: (ae-forgotten-export) The symbol "IncomingMessageRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    constructor(incomingMessageRequest: IncomingMessageRequest);
    accept(options?: ResponseOptions): Promise<void>;
    reject(options?: ResponseOptions): Promise<void>;
    get request(): IncomingRequestMessage;
}

// @public
export class Messager {
    constructor(userAgent: UserAgent, targetURI: URI, content: string, contentType?: string, options?: MessagerOptions);
    // Warning: (ae-forgotten-export) The symbol "MessagerMessageOptions" needs to be exported by the entry point index.d.ts
    message(options?: MessagerMessageOptions): Promise<void>;
    }

// @public
export interface MessagerOptions {
    extraHeaders?: Array<string>;
    // @deprecated (undocumented)
    params?: {
        fromDisplayName?: string;
        fromTag?: string;
        fromUri?: string | URI;
        toDisplayName?: string;
        toUri?: string | URI;
    };
}

// @public
export class Notification {
    // Warning: (ae-forgotten-export) The symbol "IncomingNotifyRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    constructor(incomingNotifyRequest: IncomingNotifyRequest);
    accept(options?: ResponseOptions): Promise<void>;
    reject(options?: ResponseOptions): Promise<void>;
    get request(): IncomingRequestMessage;
}

// @public
export class Publisher extends EventEmitter {
    constructor(userAgent: UserAgent, targetURI: URI, eventType: string, options?: PublisherOptions);
    dispose(): Promise<void>;
    publish(content: string, options?: PublisherPublishOptions): Promise<void>;
    // Warning: (ae-forgotten-export) The symbol "IncomingResponseMessage" needs to be exported by the entry point index.d.ts
    //
    // @internal (undocumented)
    protected receiveResponse(response: IncomingResponseMessage): void;
    // Warning: (ae-forgotten-export) The symbol "OutgoingPublishRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal (undocumented)
    protected send(): OutgoingPublishRequest;
    get state(): PublisherState;
    get stateChange(): Emitter<PublisherState>;
    unpublish(options?: PublisherUnpublishOptions): Promise<void>;
    }

// @public
export interface PublisherOptions {
    // @deprecated (undocumented)
    body?: string;
    // @deprecated (undocumented)
    contentType?: string;
    expires?: number;
    extraHeaders?: Array<string>;
    // @deprecated (undocumented)
    params?: {
        fromDisplayName?: string;
        fromTag?: string;
        fromUri?: URI;
        toDisplayName?: string;
        toUri?: URI;
    };
    unpublishOnClose?: boolean;
}

// @public
export interface PublisherPublishOptions {
}

// @public
export enum PublisherState {
    // (undocumented)
    Initial = "Initial",
    // (undocumented)
    Published = "Published",
    // (undocumented)
    Terminated = "Terminated",
    // (undocumented)
    Unpublished = "Unpublished"
}

// @public
export interface PublisherUnpublishOptions {
}

// @public
export class Referral {
    // Warning: (ae-forgotten-export) The symbol "IncomingReferRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    constructor(incomingReferRequest: IncomingReferRequest, session: Session);
    accept(options?: ResponseOptions): Promise<void>;
    makeInviter(options?: InviterOptions): Inviter;
    // (undocumented)
    get referredBy(): string | undefined;
    // (undocumented)
    get referTo(): NameAddrHeader;
    reject(options?: ResponseOptions): Promise<void>;
    // (undocumented)
    get replaces(): string | undefined;
    get request(): IncomingRequestMessage;
    }

// @public
export class Referrer {
    constructor(session: Session, referTo: URI | Session, options?: ReferrerOptions);
    delegate: ReferrerDelegate | undefined;
    // Warning: (ae-forgotten-export) The symbol "OutgoingReferRequest" needs to be exported by the entry point index.d.ts
    refer(options?: ReferrerReferOptions): Promise<OutgoingReferRequest>;
    get session(): Session;
    }

// @public
export interface ReferrerDelegate extends OutgoingRequestDelegate {
    // (undocumented)
    onNotify(notification: Notification): void;
}

// @public
export interface ReferrerOptions {
    // (undocumented)
    extraHeaders?: Array<string>;
}

// @public
export interface ReferrerReferOptions {
    requestDelegate?: ReferrerDelegate;
    requestOptions?: RequestOptions;
}

// @public
export class Registerer {
    constructor(userAgent: UserAgent, options?: RegistererOptions);
    get contacts(): Array<string>;
    dispose(): Promise<void>;
    // Warning: (ae-forgotten-export) The symbol "OutgoingRegisterRequest" needs to be exported by the entry point index.d.ts
    register(options?: RegistererRegisterOptions): Promise<OutgoingRegisterRequest>;
    get state(): RegistererState;
    get stateChange(): Emitter<RegistererState>;
    unregister(options?: RegistererUnregisterOptions): Promise<OutgoingRegisterRequest>;
    }

// @public
export interface RegistererOptions {
    expires?: number;
    extraContactHeaderParams?: Array<string>;
    extraHeaders?: Array<string>;
    instanceId?: string;
    logConfiguration?: boolean;
    // @deprecated (undocumented)
    params?: {
        fromDisplayName?: string;
        fromTag?: string;
        fromUri?: URI;
        toDisplayName?: string;
        toUri?: URI;
    };
    regId?: number;
    registrar?: URI;
}

// @public
export interface RegistererRegisterOptions {
    requestDelegate?: OutgoingRequestDelegate;
    requestOptions?: RequestOptions;
}

// @public
export enum RegistererState {
    // (undocumented)
    Initial = "Initial",
    // (undocumented)
    Registered = "Registered",
    // (undocumented)
    Terminated = "Terminated",
    // (undocumented)
    Unregistered = "Unregistered"
}

// @public
export interface RegistererUnregisterOptions {
    all?: boolean;
    requestDelegate?: OutgoingRequestDelegate;
    requestOptions?: RequestOptions;
}

// @public
export class RequestPendingError extends Exception {
    // @internal
    constructor(message?: string);
}

// @public
export abstract class Session {
    // @internal
    protected constructor(userAgent: UserAgent, options?: SessionOptions);
    // Warning: (ae-forgotten-export) The symbol "AckableIncomingResponseWithSession" needs to be exported by the entry point index.d.ts
    //
    // @internal
    protected ackAndBye(response: AckableIncomingResponseWithSession, statusCode?: number, reasonPhrase?: string): void;
    get assertedIdentity(): NameAddrHeader | undefined;
    // @internal (undocumented)
    protected _assertedIdentity: NameAddrHeader | undefined;
    // @internal
    _bye(delegate?: OutgoingRequestDelegate, options?: RequestOptions): Promise<OutgoingByeRequest>;
    // @internal (undocumented)
    _contact: string | undefined;
    data: any;
    delegate: SessionDelegate | undefined;
    get dialog(): Session_2 | undefined;
    // Warning: (ae-forgotten-export) The symbol "Session" needs to be exported by the entry point index.d.ts
    //
    // @internal (undocumented)
    protected _dialog: Session_2 | undefined;
    dispose(): Promise<void>;
    // Warning: (ae-forgotten-export) The symbol "Body" needs to be exported by the entry point index.d.ts
    //
    // @internal
    protected generateResponseOfferAnswer(request: IncomingInviteRequest, options: {
        sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
        sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    }): Promise<Body | undefined>;
    // @internal
    protected generateResponseOfferAnswerInDialog(options: {
        sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
        sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    }): Promise<Body | undefined>;
    // @internal
    protected getOffer(options: {
        sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
        sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    }): Promise<Body>;
    get id(): string;
    // @internal (undocumented)
    protected abstract _id: string;
    // @internal
    _info(delegate?: OutgoingRequestDelegate, options?: RequestOptions): Promise<OutgoingByeRequest>;
    invite(options?: SessionInviteOptions): Promise<OutgoingInviteRequest>;
    abstract readonly localIdentity: NameAddrHeader;
    protected abstract logger: Logger;
    // Warning: (ae-forgotten-export) The symbol "IncomingAckRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    protected onAckRequest(request: IncomingAckRequest): void;
    // Warning: (ae-forgotten-export) The symbol "IncomingByeRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    protected onByeRequest(request: IncomingByeRequest): void;
    // @internal
    protected onInfoRequest(request: IncomingInfoRequest): void;
    // @internal
    protected onInviteRequest(request: IncomingInviteRequest): void;
    // @internal
    protected onNotifyRequest(request: IncomingNotifyRequest): void;
    // Warning: (ae-forgotten-export) The symbol "IncomingPrackRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    protected onPrackRequest(request: IncomingPrackRequest): void;
    // @internal
    protected onReferRequest(request: IncomingReferRequest): void;
    // @internal
    refer(referrer: Referrer, delegate?: OutgoingRequestDelegate, options?: RequestOptions): Promise<OutgoingByeRequest>;
    // @internal (undocumented)
    _referral: Inviter | undefined;
    // @internal (undocumented)
    protected _referralInviterOptions: InviterOptions | undefined;
    // @internal (undocumented)
    _referrer: Referrer | undefined;
    abstract readonly remoteIdentity: NameAddrHeader;
    // @internal (undocumented)
    protected _renderbody: string | undefined;
    // @internal (undocumented)
    protected _rendertype: string | undefined;
    get replacee(): Session | undefined;
    // @internal (undocumented)
    _replacee: Session | undefined;
    // @internal
    protected rollbackOffer(): Promise<void>;
    get sessionDescriptionHandler(): SessionDescriptionHandler | undefined;
    get sessionDescriptionHandlerFactory(): SessionDescriptionHandlerFactory;
    // @internal (undocumented)
    protected _sessionDescriptionHandlerModifiers: Array<SessionDescriptionHandlerModifier> | undefined;
    // @internal (undocumented)
    protected _sessionDescriptionHandlerOptions: SessionDescriptionHandlerOptions | undefined;
    // @internal
    protected setAnswer(answer: Body, options: {
        sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
        sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    }): Promise<void>;
    // @internal
    protected setOfferAndGetAnswer(offer: Body, options: {
        sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
        sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    }): Promise<Body>;
    // @internal
    protected setSessionDescriptionHandler(sdh: SessionDescriptionHandler): void;
    // @internal
    protected setupSessionDescriptionHandler(): SessionDescriptionHandler;
    get state(): SessionState;
    get stateChange(): Emitter<SessionState>;
    // @internal
    protected stateTransition(newState: SessionState): void;
    get userAgent(): UserAgent;
    }

// @public
export interface SessionDelegate {
    onInfo?(info: Info): void;
    onInvite?(request: IncomingRequestMessage, response: string, statusCode: number): void;
    onNotify?(notification: Notification): void;
    onRefer?(referral: Referral): void;
}

// @public
export interface SessionDescriptionHandler {
    close(): void;
    getDescription(options?: SessionDescriptionHandlerOptions, modifiers?: Array<SessionDescriptionHandlerModifier>): Promise<BodyAndContentType>;
    hasDescription(contentType: string): boolean;
    holdModifier(sessionDescription: RTCSessionDescriptionInit): Promise<RTCSessionDescriptionInit>;
    rollbackDescription?(): Promise<void>;
    sendDtmf(tones: string, options?: any): boolean;
    setDescription(sdp: string, options?: SessionDescriptionHandlerOptions, modifiers?: Array<SessionDescriptionHandlerModifier>): Promise<void>;
}

// @public
export class SessionDescriptionHandlerError extends Exception {
    constructor(message?: string);
}

// @public
export interface SessionDescriptionHandlerFactory {
    (session: Session, options?: object): SessionDescriptionHandler;
}

// @public
export interface SessionDescriptionHandlerModifier {
    // (undocumented)
    (sessionDescription: RTCSessionDescriptionInit): Promise<RTCSessionDescriptionInit>;
}

// @public
export interface SessionDescriptionHandlerOptions {
    // (undocumented)
    constraints?: object;
}

// @public
export interface SessionInviteOptions {
    requestDelegate?: OutgoingRequestDelegate;
    requestOptions?: RequestOptions;
    // (undocumented)
    sessionDescriptionHandlerModifiers?: Array<SessionDescriptionHandlerModifier>;
    // (undocumented)
    sessionDescriptionHandlerOptions?: SessionDescriptionHandlerOptions;
    withoutSdp?: boolean;
}

// @public
export interface SessionOptions {
    // (undocumented)
    delegate?: SessionDelegate;
}

// @public
export enum SessionState {
    Established = "Established",
    Establishing = "Establishing",
    Initial = "Initial",
    Terminated = "Terminated",
    Terminating = "Terminating"
}

// @public
export class SessionTerminatedError extends Exception {
    constructor();
}

// @public
export enum SIPExtension {
    // (undocumented)
    Required = "Required",
    // (undocumented)
    Supported = "Supported",
    // (undocumented)
    Unsupported = "Unsupported"
}

// @public
export class StateTransitionError extends Exception {
    constructor(message?: string);
}

// @public
export class Subscriber extends Subscription {
    constructor(userAgent: UserAgent, targetURI: URI, eventType: string, options?: SubscriberOptions);
    // @internal
    dispose(): Promise<void>;
    // Warning: (ae-forgotten-export) The symbol "IncomingResponse" needs to be exported by the entry point index.d.ts
    //
    // @internal (undocumented)
    protected onAccepted(response: IncomingResponse): void;
    // @internal (undocumented)
    protected onNotify(request: IncomingNotifyRequest): void;
    // Warning: (ae-forgotten-export) The symbol "OutgoingSubscribeRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal (undocumented)
    protected onRefresh(request: OutgoingSubscribeRequest): void;
    // @internal @deprecated
    _refresh(): Promise<void>;
    subscribe(options?: SubscriberSubscribeOptions): Promise<void>;
    unsubscribe(options?: SubscriptionUnsubscribeOptions): Promise<void>;
}

// @public
export interface SubscriberOptions extends SubscriptionOptions {
    // (undocumented)
    body?: string;
    // (undocumented)
    contentType?: string;
    // (undocumented)
    expires?: number;
    // (undocumented)
    extraHeaders?: Array<string>;
}

// @public
export interface SubscriberSubscribeOptions {
}

// @public
export abstract class Subscription {
    // @internal
    protected constructor(userAgent: UserAgent, options?: SubscriptionOptions);
    data: any;
    delegate: SubscriptionDelegate | undefined;
    get dialog(): Subscription_2 | undefined;
    // Warning: (ae-forgotten-export) The symbol "Subscription" needs to be exported by the entry point index.d.ts
    //
    // @internal
    protected _dialog: Subscription_2 | undefined;
    dispose(): Promise<void>;
    // @internal
    get disposed(): boolean;
    get state(): SubscriptionState;
    get stateChange(): Emitter<SubscriptionState>;
    // @internal (undocumented)
    protected stateTransition(newState: SubscriptionState): void;
    abstract subscribe(options?: SubscriptionSubscribeOptions): Promise<void>;
    abstract unsubscribe(options?: SubscriptionUnsubscribeOptions): Promise<void>;
    // @internal
    protected _userAgent: UserAgent;
}

// @public
export interface SubscriptionDelegate {
    onNotify(notification: Notification): void;
}

// @public
export interface SubscriptionOptions {
    // (undocumented)
    delegate?: SubscriptionDelegate;
}

// @public
export enum SubscriptionState {
    // (undocumented)
    Initial = "Initial",
    // (undocumented)
    NotifyWait = "NotifyWait",
    // (undocumented)
    Subscribed = "Subscribed",
    // (undocumented)
    Terminated = "Terminated"
}

// @public
export interface SubscriptionSubscribeOptions {
}

// @public
export interface SubscriptionUnsubscribeOptions {
}

// Warning: (ae-forgotten-export) The symbol "Transport" needs to be exported by the entry point index.d.ts
//
// @public
export interface Transport extends Transport_2 {
    connect(): Promise<void>;
    disconnect(): Promise<void>;
    dispose(): Promise<void>;
    isConnected(): boolean;
    onConnect: (() => void) | undefined;
    onDisconnect: ((error?: Error) => void) | undefined;
    onMessage: ((message: string) => void) | undefined;
    send(message: string): Promise<void>;
    readonly state: TransportState;
    readonly stateChange: Emitter<TransportState>;
}

// @public
export enum TransportState {
    Connected = "Connected",
    Connecting = "Connecting",
    Disconnected = "Disconnected",
    Disconnecting = "Disconnecting"
}

// @public
export class UserAgent {
    constructor(options?: Partial<UserAgentOptions>);
    get configuration(): Required<UserAgentOptions>;
    // Warning: (ae-forgotten-export) The symbol "Contact" needs to be exported by the entry point index.d.ts
    get contact(): Contact;
    data: any;
    delegate: UserAgentDelegate | undefined;
    getLogger(category: string, label?: string): Logger;
    // Warning: (ae-forgotten-export) The symbol "LoggerFactory" needs to be exported by the entry point index.d.ts
    getLoggerFactory(): LoggerFactory;
    isConnected(): boolean;
    // @internal
    _makeInviter(targetURI: URI, options?: InviterOptions): Inviter;
    static makeURI(uri: string): URI | undefined;
    // @internal (undocumented)
    _publishers: {
        [id: string]: Publisher;
    };
    reconnect(): Promise<void>;
    // @internal (undocumented)
    _registerers: {
        [id: string]: Registerer;
    };
    // @internal (undocumented)
    _sessions: {
        [id: string]: Session;
    };
    start(): Promise<void>;
    get state(): UserAgentState;
    get stateChange(): Emitter<UserAgentState>;
    stop(): Promise<void>;
    // @internal (undocumented)
    _subscriptions: {
        [id: string]: Subscription;
    };
    get transport(): Transport;
    // Warning: (ae-forgotten-export) The symbol "UserAgentCore" needs to be exported by the entry point index.d.ts
    get userAgentCore(): UserAgentCore;
    }

// @public
export interface UserAgentDelegate {
    onConnect?(): void;
    onDisconnect?(error?: Error): void;
    onInvite?(invitation: Invitation): void;
    onMessage?(message: Message): void;
    onNotify?(notification: Notification): void;
    onRefer?(referral: Referral): void;
    // Warning: (ae-forgotten-export) The symbol "IncomingRegisterRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    onRegisterRequest?(request: IncomingRegisterRequest): void;
    onSubscribe?(subscription: Subscription): void;
    // Warning: (ae-forgotten-export) The symbol "IncomingSubscribeRequest" needs to be exported by the entry point index.d.ts
    //
    // @internal
    onSubscribeRequest?(request: IncomingSubscribeRequest): void;
}

// @public
export interface UserAgentOptions {
    allowLegacyNotifications?: boolean;
    allowOutOfDialogRefers?: boolean;
    authorizationPassword?: string;
    authorizationUsername?: string;
    // @deprecated (undocumented)
    autoStart?: boolean;
    autoStop?: boolean;
    delegate?: UserAgentDelegate;
    displayName?: string;
    forceRport?: boolean;
    // @deprecated
    hackAllowUnregisteredOptionTags?: boolean;
    // @deprecated
    hackIpInContact?: boolean | string;
    // @deprecated
    hackViaTcp?: boolean;
    // @deprecated
    hackWssInTransport?: boolean;
    logBuiltinEnabled?: boolean;
    logConfiguration?: boolean;
    logConnector?: LogConnector;
    logLevel?: LogLevel;
    noAnswerTimeout?: number;
    preloadedRouteSet?: Array<string>;
    // @deprecated (undocumented)
    reconnectionAttempts?: number;
    // @deprecated (undocumented)
    reconnectionDelay?: number;
    sessionDescriptionHandlerFactory?: SessionDescriptionHandlerFactory;
    sessionDescriptionHandlerFactoryOptions?: object;
    sipExtension100rel?: SIPExtension;
    sipExtensionExtraSupported?: Array<string>;
    sipExtensionReplaces?: SIPExtension;
    sipjsId?: string;
    transportConstructor?: new (logger: any, options: any) => Transport;
    transportOptions?: any;
    uri?: URI;
    userAgentString?: string;
    viaHost?: string;
}

// @public
export const UserAgentRegisteredOptionTags: {
    [option: string]: boolean;
};

// @public
export enum UserAgentState {
    // (undocumented)
    Started = "Started",
    // (undocumented)
    Stopped = "Stopped"
}


```