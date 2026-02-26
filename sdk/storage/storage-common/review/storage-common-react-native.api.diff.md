# API Report Diff for react-native runtime

This file contains only the differences from the Node.js API.
For the complete API surface, see the corresponding -node.api.md file.

```diff
===================================================================
--- NodeJS
+++ react-native
@@ -36,12 +36,10 @@
     abstract sendRequest(webResource: WebResourceLike): Promise<CompatResponse>;
     shouldLog(logLevel: HttpPipelineLogLevel): boolean;
 }
 
-// @public
+// @public (undocumented)
 export class BufferScheduler {
-    constructor(readable: NodeJS.ReadableStream, bufferSize: number, maxBuffers: number, outgoingHandler: OutgoingHandler, concurrency: number, encoding?: BufferEncoding);
-    do(): Promise<void>;
 }
 
 // @public
<<<<<<< HEAD
 export abstract class Credential implements RequestPolicyFactory {
@@ -67,11 +65,8 @@
     destroy(error?: Error): this;
 }
=======
 abstract class Credential_2 implements RequestPolicyFactory {
@@ -67,11 +65,8 @@
 // @public
 export function NewRetryPolicyFactory(retryOptions?: StorageRetryOptions): RequestPolicyFactory;
>>>>>>> fc0eb7e65c (STG101)
 
 // @public
-export type OutgoingHandler = (body: () => NodeJS.ReadableStream, length: number, offset?: number) => Promise<any>;
-
-// @public
 export class StorageBrowserPolicy extends BaseRequestPolicy {
     constructor(nextPolicy: RequestPolicy, options: RequestPolicyOptionsLike);
     sendRequest(request: WebResourceLike): Promise<CompatResponse>;
 }
<<<<<<< HEAD
@@ -134,14 +129,10 @@
=======
@@ -149,14 +144,10 @@
>>>>>>> fc0eb7e65c (STG101)
     EXPONENTIAL = 0,
     FIXED = 1
 }
 
-// @public
-export class StorageSharedKeyCredential extends Credential_2 {
-    constructor(accountName: string, accountKey: string);
-    readonly accountName: string;
-    computeHMACSHA256(stringToSign: string): string;
-    create(nextPolicy: RequestPolicy, options: RequestPolicyOptionsLike): StorageSharedKeyCredentialPolicy;
+// @public (undocumented)
+export class StorageSharedKeyCredential {
 }
 
 // @public
 export class StorageSharedKeyCredentialPolicy extends CredentialPolicy {
<<<<<<< HEAD
@@ -149,9 +140,9 @@
=======
@@ -164,9 +155,9 @@
>>>>>>> fc0eb7e65c (STG101)
     protected signRequest(request: WebResourceLike): WebResourceLike;
 }
 
 // @public
-export function storageSharedKeyCredentialPolicy(options: StorageSharedKeyCredentialPolicyOptions): PipelinePolicy;
+export function storageSharedKeyCredentialPolicy(_options: StorageSharedKeyCredentialPolicyOptions): PipelinePolicy;
 
 // @public
 export const storageSharedKeyCredentialPolicyName = "storageSharedKeyCredentialPolicy";
 
<<<<<<< HEAD
@@ -162,25 +153,10 @@
     // (undocumented)
     accountName: string;
=======
@@ -200,26 +191,10 @@
     doInjectErrorOnce?: boolean;
     highWaterMark?: number;
>>>>>>> fc0eb7e65c (STG101)
 }
 
-// @public
-export interface UserDelegationKey {
-    signedDelegatedUserTid: string | undefined;
-    signedExpiresOn: Date;
-    signedObjectId: string;
-    signedService: string;
-    signedStartsOn: Date;
-    signedTenantId: string;
-    signedVersion: string;
-    value: string;
-}
-
-// @public
+// @public (undocumented)
 export class UserDelegationKeyCredential {
-    constructor(accountName: string, userDelegationKey: UserDelegationKey);
-    readonly accountName: string;
-    computeHMACSHA256(stringToSign: string): string;
-    readonly userDelegationKey: UserDelegationKey;
 }
 
 // (No @packageDocumentation comment for this package)
 

```