2017.08 - version 0.12.3-preview

ALL
* Added Nokogiri as a gem into Gemfile, resolving an issue where bundler failed to recognize that the dependency exists after installation.

2017.08 - version 0.12.2-preview

ALL
* Removed Nokogiri as a dependency to resolve conflict version caused by azure-core also depending on Nokogiri.

2017.04 - version 0.12.1-preview

ALL
* Relaxed constraint on Nokogiri version dependency to allow Nokogiri 1.7.x for Ruby 2.1 and later, but preserving support for Ruby 1.9.3. (Note that this may require updating to Bundler 1.13 or later if you're using Ruby 1.9 or 2.0.)

2017.02 - version 0.12.0-preview

ALL
* Fixed the issue where `should_retry?` in the retry_filter.rb overwrites the result from derived `apply_retry_policy`. [#76](https://github.com/Azure/azure-storage-ruby/issues/76)
* Fixed the issue where `Azure::Storage::Client.create_from_connection_string` throws an exception. [#77](https://github.com/Azure/azure-storage-ruby/issues/77)
* Added the support for setting the "timeout" option in `get_service_properties` and `set_service_properties`.

BLOB
* Added the metadata to the returning instance when creates a blob.
* Added `transactional_md5` to the options of `put_blob_pages`.

FILE
* Added File Service support, targeting storage service version 2015-04-05.

2016.12 - version 0.11.5-preview

ALL
* Added the support for setting customer user agent. [#71](https://github.com/Azure/azure-storage-ruby/issues/71)
* Added the support for hooking in sending requests.

2016.11 - version 0.11.4-preview

ALL
* Removed the unnecessary dependencies. [#55](https://github.com/Azure/azure-storage-ruby/issues/55), [#67](https://github.com/Azure/azure-storage-ruby/issues/67)

BLOB
* Fixed the issue when checking the content encoding.
* Fixed the wrong "Content-Encoding" value in the test cases.
* Fixed the issue where it cannot use the `create_block_blob` method with an IO/File object. [#61](https://github.com/Azure/azure-storage-ruby/issues/61)

2016.10 - version 0.11.3-preview

ALL
* Fixed an issue in retry policies.

2016.10 - version 0.11.2-preview

ALL
* Fixed the issue where it retries on HTTP 4xx errors.

BLOB
* Fixed the issue of wrong "Content-Encoding". [#49](https://github.com/Azure/azure-storage-ruby/issues/49)

2016.09 - version 0.11.1-preview

ALL
* Added the support for setting the client request ID via the "request_id" parameter.
* Added the retry for the timeout errors.
* Added the retry for the connection reset error.

BLOB
* Fixed the issue where "list_blobs" doesn't work when delimiter is specified. [#41](https://github.com/Azure/azure-storage-ruby/issues/41)

2016.08 - version 0.11.0-preview

ALL
* Added the support for the account shared access signature.
* Removed the support for the Shared Key Lite.

BLOB
* Added the support for the "add"  and "create" permissions in the blob service shared access signature.

FILE
* Added the support for the "create" permission in the file service shared access signature.

2016.06 - version 0.10.2-preview

ALL
* Fixed the issue that cannot run against storage emulator on Windows.
* Fixed the issue that it doesn't run as a singleton when it calls Azure::Storage.setup.
* Updated to storage service version 2015-04-05.

2016.05 - version 0.10.1-preview

ALL
* Replaced the core module by the 'azure-core' gem.
* Stopped maintaining the support for Ruby 1.9.
* Added support for retry filters.

2016.03 - version 0.10.0-preview

ALL
* Separated out parts of Azure Storage previously found in the Azure SDK 0.7.0 to establish an independent release cycle.
* Supported Ruby 1.9.3, 2.0, 2.1 and 2.2.
* Updated to storage service version 2015-02-21. 
* Fixed issue where previous query's parameters were used, causing authentication to fail (https://github.com/Azure/azure-sdk-for-ruby/issues/276).
* Fixed the issue that the Content-MD5 is overwritten when request body exists, regardless the input value.
* Refined the code for setting service properties to be compatible with the XML schema.

BLOB
* Added support for container lease operations.
* Added support for changing the ID of an existing lease.
* Added support for copying from source blob URI.
* Added support for aborting copying a blob.
* Added support for creating an append blob.
* Added support for appending a block to an appendblob.
* Added support for the content disposition property of a blob.
* Added support for resizing a page blob.
* Added support for setting a page blob's sequence number.
* Fixed the issue where conditional headers for some APIs could not be set.
* Fixed the issue where the request fails when calling list_page_blob_ranges with start range and end range.
* Renamed create_blob_block to put_blob_block.
* Renamed create_blob_pages to put_blob_pages.
