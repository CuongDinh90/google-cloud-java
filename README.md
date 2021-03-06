Google Cloud Client Library for Java
==========================

Java idiomatic client for [Google Cloud Platform][cloud-platform] services.

[![Build Status](https://travis-ci.org/GoogleCloudPlatform/google-cloud-java.svg?branch=master)](https://travis-ci.org/GoogleCloudPlatform/google-cloud-java)
[![Coverage Status](https://coveralls.io/repos/GoogleCloudPlatform/google-cloud-java/badge.svg?branch=master)](https://coveralls.io/r/GoogleCloudPlatform/google-cloud-java?branch=master)
[![Maven](https://img.shields.io/maven-central/v/com.google.cloud/google-cloud.svg)](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.google.cloud%22%20a%3A%22google-cloud%22)
[![Codacy Badge](https://api.codacy.com/project/badge/grade/9da006ad7c3a4fe1abd142e77c003917)](https://www.codacy.com/app/mziccard/google-cloud-java)
[![Dependency Status](https://www.versioneye.com/user/projects/58fe4c8d6ac171426c414772/badge.svg?style=flat)](https://www.versioneye.com/user/projects/58fe4c8d6ac171426c414772)

-  [Homepage](https://googlecloudplatform.github.io/google-cloud-java/)
-  [API Documentation](https://googlecloudplatform.github.io/google-cloud-java/apidocs)

This client supports the following Google Cloud Platform services at a [GA](#versioning) quality level:
-  [Stackdriver Logging](google-cloud-logging) (GA)
-  [Cloud Datastore](google-cloud-datastore) (GA)
-  [Cloud Storage](google-cloud-storage) (GA)
-  [Cloud Translation](google-cloud-translate) (GA)

This client supports the following Google Cloud Platform services at a [Beta](#versioning) quality level:

-  [BigQuery](google-cloud-bigquery) (Beta)
-  [Cloud Pub/Sub](google-cloud-pubsub) (Beta)
-  [Cloud Spanner](google-cloud-spanner) (Beta)
-  [Cloud Natural Language](google-cloud-language) (Beta)
-  [Cloud Vision](google-cloud-vision) (Beta)

This client supports the following Google Cloud Platform services at an [Alpha](#versioning) quality level:

-  [Cloud Compute](google-cloud-compute) (Alpha)
-  [Cloud Data Loss Prevention](google-cloud-dlp) (Alpha)
-  [Cloud DNS](google-cloud-dns) (Alpha)
-  [Stackdriver Error Reporting](google-cloud-errorreporting) (Alpha)
-  [Stackdriver Monitoring](google-cloud-monitoring) (Alpha)
-  [Cloud Resource Manager](google-cloud-resourcemanager) (Alpha)
-  [Cloud Speech](google-cloud-speech) (Alpha)
-  [Cloud Trace](google-cloud-trace) (Alpha)
-  [Cloud Video Intelligence](google-cloud-video-intelligence) (Alpha)

> Note: google-cloud-java is a work-in-progress, and may occasionally
> make backwards-incompatible changes.

Quickstart
----------

If you are using Maven, add this to your pom.xml file
```xml
<dependency>
  <groupId>com.google.cloud</groupId>
  <artifactId>google-cloud</artifactId>
  <version>0.21.1-alpha</version>
</dependency>
```
If you are using Gradle, add this to your dependencies
```Groovy
compile 'com.google.cloud:google-cloud:0.21.1-alpha'
```
If you are using SBT, add this to your dependencies
```Scala
libraryDependencies += "com.google.cloud" % "google-cloud" % "0.21.1-alpha"
```

For running on Google App Engine, see [more instructions here](./APPENGINE.md).

Resolving dependency conflicts
----------
Optionally, if you encounter dependency conflicts, you may specify google-cloud-pom as a ["bill of materials"](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html#Importing_Dependencies) to ensure that internal dependencies of google-cloud and your project are in sync.

If you are using Maven, add this to your pom.xml file
```xml
<dependencyManagement>
  <dependencies>
    <dependency>
      <groupId>com.google.cloud</groupId>
      <artifactId>google-cloud-pom</artifactId>
      <version>0.21.1-alpha</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>
  </dependencies>
</dependencyManagement>
```
If you are using Gradle, add the following plugin at the beginning of your build.gradle file

```Groovy
plugins {
  id "io.spring.dependency-management" version "1.0.3.RELEASE"
}
```
Then add the following in your build.gradle file
```Groovy
dependencyManagement {
  imports {
    mavenBom 'com.google.cloud:google-cloud-pom:0.21.1-alpha'
  }
}
```    

Example Applications
--------------------

- [`BigQueryExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/bigquery/BigQueryExample.java) - A simple command line interface providing some of Cloud BigQuery's functionality
  - Read more about using this application on the [`BigQueryExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/bigquery/BigQueryExample.html).
- [`ComputeExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/compute/ComputeExample.java) - A simple command line interface providing some of Cloud Compute's functionality
  - Read more about using this application on the [`google-cloud-examples` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/compute/ComputeExample.html).
- [`Bookshelf`](https://github.com/GoogleCloudPlatform/getting-started-java/tree/master/bookshelf) - An App Engine app that manages a virtual bookshelf.
  - This app uses `google-cloud` to interface with Cloud Datastore and Cloud Storage. It also uses Cloud SQL, another Google Cloud Platform service.
- [`DatastoreExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/datastore/DatastoreExample.java) - A simple command line interface for Cloud Datastore
  - Read more about using this application on the [`DatastoreExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/datastore/DatastoreExample.html).
- [`DnsExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/dns/DnsExample.java) - A simple command line interface for Cloud DNS
  - Read more about using this application on the [`DnsExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/dns/DnsExample.html).
- [`Flexible Environment/Datastore example`](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/flexible/datastore) - A simple app that uses Cloud Datastore to list the last 10 IP addresses that visited your site.
  - Read about how to run the application [here](https://github.com/GoogleCloudPlatform/java-docs-samples/blob/master/managed_vms/README.md).
- [`Flexible Environment/Storage example`](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/flexible/cloudstorage) - An app that uploads files to a public Cloud Storage bucket on the App Engine Flexible Environment runtime.
- [`GuestBook`](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/appengine/guestbook-cloud-datastore) - An App Engine Standard guestbook that uses Cloud Datastore.
- [`LoggingExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/logging/LoggingExample.java) - A simple command line interface providing some of Stackdriver Logging's functionality
  - Read more about using this application on the [`LoggingExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/logging/LoggingExample.html).
- [`ResourceManagerExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/resourcemanager/ResourceManagerExample.java) - A simple command line interface providing some of Cloud Resource Manager's functionality
  - Read more about using this application on the [`ResourceManagerExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/resourcemanager/ResourceManagerExample.html).
- [`SparkDemo`](https://github.com/GoogleCloudPlatform/java-docs-samples/blob/master/flexible/sparkjava) - An example of using `google-cloud-datastore` from within the SparkJava and App Engine Flexible Environment frameworks.
  - Read about how it works on the example's [README page](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/managed_vms/sparkjava#how-does-it-work).
- [`StorageExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/storage/StorageExample.java) - A simple command line interface providing some of Cloud Storage's functionality
  - Read more about using this application on the [`StorageExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/storage/StorageExample.html).
- [`TaskList`](https://github.com/GoogleCloudPlatform/java-docs-samples/blob/master/datastore/src/main/java/com/google/datastore/snippets/TaskList.java) - A command line application that uses Cloud Datastore to manage a to-do list.
  - Read about how to run the application on its [README page](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/datastore).
- [`TranslateExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/translate/TranslateExample.java) - A simple command line interface providing some of Google Translation's functionality
  - Read more about using this application on the [`TranslateExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/translate/TranslateExample.html).

Specifying a Project ID
-----------------------

Most `google-cloud` libraries require a project ID.  There are multiple ways to specify this project ID.

1. When using `google-cloud` libraries from within Compute/App Engine, there's no need to specify a project ID.  It is automatically inferred from the production environment.
2. When using `google-cloud` elsewhere, you can do one of the following:
  * Supply the project ID when building the service options.  For example, to use Datastore from a project with ID "PROJECT_ID", you can write:

  ```java
  Datastore datastore = DatastoreOptions.newBuilder().setProjectId("PROJECT_ID").build().getService();
  ```
  * Specify the environment variable `GOOGLE_CLOUD_PROJECT` to be your desired project ID.
  * Set the project ID using the [Google Cloud SDK](https://cloud.google.com/sdk/?hl=en).  To use the SDK, [download the SDK](https://cloud.google.com/sdk/?hl=en) if you haven't already, and set the project ID from the command line.  For example:

  ```
  gcloud config set project PROJECT_ID
  ```

`google-cloud` determines the project ID from the following sources in the listed order, stopping once it finds a value:

1. The project ID supplied when building the service options
2. Project ID specified by the environment variable `GOOGLE_CLOUD_PROJECT`
3. The App Engine project ID
4. The project ID specified in the JSON credentials file pointed by the `GOOGLE_APPLICATION_CREDENTIALS` environment variable
5. The Google Cloud SDK project ID
6. The Compute Engine project ID

In cases where the library may expect a project ID explicitly, we provide a helper that can provide the inferred project ID:
   ```java
     import com.google.cloud.ServiceOptions;
     ...
     String projectId = ServiceOptions.getDefaultProjectId();
   ```

Authentication
--------------

`google-cloud-java` uses
[https://github.com/google/google-auth-library-java](https://github.com/google/google-auth-library-java)
to authenticate requests. `google-auth-library-java` supports a wide range of authentication types;
see the project's [README](https://github.com/google/google-auth-library-java/blob/master/README.md)
and [javadoc](http://google.github.io/google-auth-library-java/releases/0.6.0/apidocs/) for more
details.

To access Google Cloud services, you first need to ensure that the necessary Google Cloud APIs are
enabled for your project. To do this, follow the instructions on the
[authentication document](https://github.com/GoogleCloudPlatform/gcloud-common/blob/master/authentication/readme.md#authentication)
shared by all the Google Cloud language libraries.

Next, choose a method for authenticating API requests from within your project:

1. When using `google-cloud` libraries from within Compute/App Engine, no additional authentication
steps are necessary. For example:
```java
Storage storage = StorageOptions.getDefaultInstance().getService();
```
2. When using `google-cloud` libraries elsewhere, there are several options:
  * [Generate a JSON service account key](https://cloud.google.com/storage/docs/authentication?hl=en#service_accounts).
  After downloading that key, you must do one of the following:
    * Define the environment variable GOOGLE_APPLICATION_CREDENTIALS to be the location of the key.
    For example:
    ```bash
    export GOOGLE_APPLICATION_CREDENTIALS=/path/to/my/key.json
    ```
    * Supply the JSON credentials file when building the service options. For example, this Storage
    object has the necessary permissions to interact with your Google Cloud Storage data:
    ```java
    Storage storage = StorageOptions.newBuilder()
        .setCredentials(ServiceAccountCredentials.fromStream(new FileInputStream("/path/to/my/key.json")))
        .build()
        .getService();
    ```
  * If running locally for development/testing, you can use the
  [Google Cloud SDK](https://cloud.google.com/sdk/). Create Application Default Credentials with
  `gcloud auth application-default login`, and then `google-cloud` will automatically detect such
  credentials.
  * If you already have an OAuth2 access token, you can use it to authenticate (notice that in this
  case, the access token will not be automatically refreshed):
  ```java
  Storage storage = StorageOptions.newBuilder()
      .setCredentials(new GoogleCredentials(new AccessToken(accessToken, expirationTime)))
      .build()
      .getService();
  ```

If no credentials are provided, `google-cloud` will attempt to detect them from the environment
using `GoogleCredentials.getApplicationDefault()` which will search for Application Default
Credentials in the following locations (in order):

1. The credentials file pointed to by the `GOOGLE_APPLICATION_CREDENTIALS` environment variable
2. Credentials provided by the Google Cloud SDK `gcloud auth application-default login` command
3. Google App Engine built-in credentials
4. Google Cloud Shell built-in credentials
5. Google Compute Engine built-in credentials

Troubleshooting
---------------

To get help, follow the instructions in the [shared Troubleshooting document](https://github.com/GoogleCloudPlatform/gcloud-common/blob/master/troubleshooting/readme.md#troubleshooting).

Using a proxy
-------------
Clients in this repository use either HTTP or gRPC for the transport layer.
The README of each client documents the transport layer the client uses.

For HTTP clients, a proxy can be configured by using `http.proxyHost` and
related system properties as documented by
[Java Networking and Proxies](https://docs.oracle.com/javase/8/docs/technotes/guides/net/proxies.html).

For gRPC clients, a proxy can be configured by using the
`GRPC_PROXY_EXP` environment variable as documented by
the gRPC [release notes](https://github.com/grpc/grpc-java/releases/tag/v1.0.3).
Please note that gRPC proxy support is currently experimental.

Java Versions
-------------

Java 7 or above is required for using the clients in this repository.

Supported Platforms
-------------------

Clients in this repository use either HTTP or gRPC for the transport layer. All
HTTP-based clients should work in all environments.

For clients that use gRPC, the supported platforms are constrained by the platforms
that [Forked Tomcat Native](http://netty.io/wiki/forked-tomcat-native.html) supports,
which for architectures means only x86_64, and for operating systems means Mac OS X,
Windows, and Linux. Additionally, gRPC constrains the use of platforms with
threading restrictions.

Thus, the following are not supported:

- Android
- Alpine Linux (due to netty-tcnative requiring glibc, which is not present on Alpine)
- Raspberry Pi (since it runs on the ARM architecture)
- Google App Engine Standard Java 7

The following environments should work (among others):

- standalone Windows on x86_64
- standalone Mac OS X on x86_64
- standalone Linux on x86_64
- Google Compute Engine (GCE)
- Google Container Engine (GKE)
- Google App Engine Standard Java 8 (GAE Std J8)
- Google App Engine Flex (GAE Flex)

Testing
-------

This library provides tools to help write tests for code that uses google-cloud services.

See [TESTING] to read more about using our testing helpers.

Versioning
----------

This library follows [Semantic Versioning](http://semver.org/), but with some
additional qualifications:

1. Components marked with `@BetaApi` are considered to be "0.x" features inside
   a "1.x" library. This means they can change between minor and patch releases
   in incompatible ways. These features should not be used by any library "B"
   that itself has consumers, unless the components of library B that use
   `@BetaApi` features are also marked with `@BetaApi`. Features marked as
   `@BetaApi` are on a path to eventually become "1.x" features with the marker
   removed.

   **Special exception for google-cloud-java**: google-cloud-java is
   allowed to depend on `@BetaApi` features in gax-java without declaring the consuming
   code `@BetaApi`, because gax-java and google-cloud-java move in step
   with each other. For this reason, gax-java should not be used
   independently of google-cloud-java.

1. Components marked with `@InternalApi` are technically public, but are only
   public for technical reasons, because of the limitations of Java's access
   modifiers. For the purposes of semver, they should be considered private.

Please note it is currently under active development. Any release versioned 0.x.y is
subject to backwards incompatible changes at any time.

**GA**: Libraries defined at a GA quality level are expected to be stable and all updates in the
libraries are guaranteed to be backwards-compatible. Any backwards-incompatible changes will lead
to the major version increment (1.x.y -> 2.0.0).

**Beta**: Libraries defined at a Beta quality level are expected to be mostly stable and
we're working towards their release candidate. We will address issues and requests with
a higher priority.

**Alpha**: Libraries defined at an Alpha quality level are still a work-in-progress and
are more likely to get backwards-incompatible updates.

Contributing
------------

Contributions to this library are always welcome and highly encouraged.

See `google-cloud`'s [CONTRIBUTING] documentation and the [shared documentation](https://github.com/GoogleCloudPlatform/gcloud-common/blob/master/contributing/readme.md#how-to-contribute-to-gcloud) for more information on how to get started.

Please note that this project is released with a Contributor Code of Conduct. By participating in this project you agree to abide by its terms. See [Code of Conduct][code-of-conduct] for more information.

License
-------

Apache 2.0 - See [LICENSE] for more information.


[CONTRIBUTING]:https://github.com/GoogleCloudPlatform/google-cloud-java/blob/master/CONTRIBUTING.md
[code-of-conduct]:https://github.com/GoogleCloudPlatform/google-cloud-java/blob/master/CODE_OF_CONDUCT.md#contributor-code-of-conduct
[LICENSE]: https://github.com/GoogleCloudPlatform/google-cloud-java/blob/master/LICENSE
[TESTING]: https://github.com/GoogleCloudPlatform/google-cloud-java/blob/master/TESTING.md
[cloud-platform]: https://cloud.google.com/
