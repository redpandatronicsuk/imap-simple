# Change Log

All notable changes to this project will be documented in this file.

## 3.0.0 - 2016-10-26

#### Fixed

- The ConnectionTimeoutError previously had its name set to 'BaseUrlNotSetError'.
This version fixes that, but since the error was part of the library's public API
and the name is technically something people could code against, the version has
received a major bump.

## 2.0.0 - 2016-09-28

Updated dependencies.

#### Changed

- The `es6-promise` module has changed its scheduler from `setImmediate()` to
`nextTick()` on Node 0.10. This directly affects this module's promise API,
so the major version has been bumped to indicate this. See
[the es6-promise changelog](https://github.com/stefanpenner/es6-promise/blob/master/CHANGELOG.md#300)
for more details about the change.

## 1.6.3 - 2016-07-20

#### Fixed

- \#15 - @johnkawakami - Parts of an email with 'BINARY' encoding will now be
    decoded as such.

## 1.6.2 - 2016-05-17

#### Fixed

- \#11 - @nytr0gen - Library will now reject properly when a close or end event
    is received when trying to connect.

## 1.6.1 - 2016-04-25

#### Fixed

- \#10 - @tuomastanner - fixed issue with decoding utf8 parts, specifically with
    respect to interacting with gmail.


## 1.6.0 - 2016-03-11

#### Added

- \#9 - @bvschwartz - `getPartData` is now using [iconv-lite][iconv-lite] to automatically
    decode message parts with an '8BIT' encoding, with a default 'utf-8' encoding set.

[iconv-lite]: https://github.com/ashtuchkin/iconv-lite

## 1.5.2 - 2016-02-04

#### Fixed

- \#7 - @srinath-imaginea - `fetchOptions` is now properly passed when using the callback
    api of `search()`

## 1.5.1 - 2015-12-04

#### Fixed

- \#5 - @jbilcke - fixed incompatible use of all upper-case encoding name, instead of treating
    the encoding as case-insensitive.

## 1.5.0 - 2015-05-22

#### Added

- added `addMessageLabel` and `moveMessage` wrapper methods to ImapSimple class

## 1.4.0 - 2015-05-22

#### Added

- added `getParts` to module export and `getPartData` to ImapSimple class

#### Fixed

- fixed strange bug where header was sometimes not being parsed

## 1.3.2 - 2015-03-06

#### Fixed

- fixed property used to determine whether an error was an authTimeout

## 1.3.1 - 2015-03-04

#### Fixed

- fixed `connect()` option `imap.authTimeout` default not being properly set.

## 1.3.0 - 2015-03-04

#### Removed

- removed `options.connectTimeout`. Support has remained for backwards
    compatibility, but the recommended option for setting a connection timeout
    moving forward is `options.imap.authTimeout`. Support for
    `options.connectTimeout` will be removed on the next major release.

## 1.2.0 - 2015-03-02

#### Added

- made `ImapSimple` an event emitter

## 1.1.2 - 2015-03-02

#### Fixed

- Put ECONNRESET error in better place, and only ignored error when calling .end()
- 'ready' and 'error' event handlers will now only fire once when connecting

## 1.1.1 - 2015-02-27

#### Fixed

- Put in basic fix for ECONNRESET error when calling .end()

## 1.1.0 - 2015-02-27

#### Added

- added .end() method to `ImapSimple` for disconnecting from imap server

## 1.0.0 - 2015-02-27

#### Added

- Initial commit.

For more information about keeping a changelog, check out [keepachangelog.com/](http://keepachangelog.com/)
