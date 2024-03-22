# Glide SSL HandshakeException Solution

This repository provides a solution to resolve the SSL HandshakeException issue encountered with Glide when loading images via URL into an ImageView.

## Error Message
```
javax.net.ssl.SSLHandshakeException: java.security.cert
.CertPathValidatorException: Trust anchor for certification path not found
```

## Dependencies
Ensure the following Glide dependencies are added to your build.gradle file:

```
implementation 'com.github.bumptech.glide:glide:4.11.0'
implementation 'com.github.bumptech.glide:annotations:4.11.0'
implementation "com.github.bumptech.glide:okhttp3-integration:4.11.0"
annotationProcessor 'com.github.bumptech.glide:compiler:4.11.0'
```
## Implementation
1. Add the classes MyGlideAppModule.kt and UnsafeOkHttpClient.kt to your project. For Java projects, equivalent Java code can be added.

2. Update your AndroidManifest.xml inside the application tag with the following metadata:

```
<application>
  <meta-data android:name="${applicationId}.network.MyGlideAppModule" android:value="AppGlideModule" />
</application>
```

Now you can load images from a URL into an ImageView using the following code:

```
Glide.with(context).load("Image Url").into(imageView);
```
