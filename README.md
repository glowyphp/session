<h1 align="center">Session Component</h1>

<p align="center">
<a href="https://github.com/atomastic/session/releases"><img alt="Version" src="https://img.shields.io/github/release/atomastic/session.svg?label=version&color=green"></a> <a href="https://github.com/atomastic/session"><img src="https://img.shields.io/badge/license-MIT-blue.svg?color=green" alt="License"></a> <a href="https://github.com/atomastic/session"><img src="https://img.shields.io/github/downloads/atomastic/session/total.svg?color=green" alt="Total downloads"></a> <img src="https://github.com/atomastic/session/workflows/Static%20Analysis/badge.svg?branch=dev"> <img src="https://github.com/atomastic/session/workflows/Tests/badge.svg">
  <a href="https://app.codacy.com/gh/atomastic/session?utm_source=github.com&utm_medium=referral&utm_content=atomastic/session&utm_campaign=Badge_Grade_Dashboard"><img src="https://api.codacy.com/project/badge/Grade/72b4dc84c20145e1b77dc0004a3c8e3d"></a>
</p>

<br>

* [Installation](#installation)
* [Usage](#usage)
* [Methods](#methods)
* [Tests](#tests)
* [License](#license)

### Installation

#### With [Composer](https://getcomposer.org)

```
composer require atomastic/session
```

### Usage

```php
use Atomastic\Session\Session;

// Create the session object.
$session = new Session();

// Set session options.
$session->setOptions([
    'use_cookies' => 1,
    'cookie_secure' => 1,
    'use_only_cookies' => 1,
    'cookie_httponly' => 1,
    'use_strict_mode' => 1,
    'sid_bits_per_character' => 5,
    'sid_length' => 48,
    'cache_limiter' => 'nocache',
    'cookie_samesite' => 'Lax'
]);

/// Start session.
$session->start();
```

### Methods

| Method | Description |
|---|---|
| <a href="#session_all">`all()`</a> | Gets all session values as array. |
| <a href="#session_close">`close()`</a> | Force the session to be saved and closed. Session data is usually stored after your script terminated without the need to call close(), but as session data is locked to prevent concurrent writes only one script may operate on a session at any time. When using framesets together with sessions you will experience the frames loading one by one due to this locking. You can reduce the time needed to load all the frames by ending the session as soon as all changes to session variables are done. |
| <a href="#session_delete">`delete()`</a> | Deletes an attribute by key. |
| <a href="#session_destroy">`destroy()`</a> | Invalidates the current session. Clears all session data and regenerates session ID. |
| <a href="#session_flush">`flush()`</a> | Flush all session data. |
| <a href="#session_get">`get()`</a> | Gets an attribute by key. |
| <a href="#session_getId">`getId()`</a> | Returns the session ID. |
| <a href="#session_getOptions">`getOptions()`</a> | Get session runtime configuration. |
| <a href="#session_getName">`getName()`</a> | Returns the session name. |
| <a href="#session_getCookieParams">`getCookieParams()`</a> | Get cookie parameters. |
| <a href="#session_has">`has()`</a> | Returns true if the key exists. |
| <a href="#session_isStarted">`isStarted()`</a> | Checks if the session was started. |
| <a href="#session_pull">`pull()`</a> | Gets an session attribute by key and remove it. |
| <a href="#session_regenerateId">`regenerateId()`</a> | Regenerates the session ID. Migrates the current session to a new session id while maintaining all session attributes. |
| <a href="#session_setId">`setId()`</a> | Sets the session ID. |
| <a href="#session_setName">`setName()`</a> | Sets the session name. |
| <a href="#session_set">`set()`</a> | Sets an session attribute by key. |
| <a href="#session_setOptions">`setOptions()`</a> | Set session runtime configuration. |
| <a href="#session_setCookieParams">`setCookieParams()`</a> | Set cookie parameters. |
| <a href="#session_start">`start()`</a> | Starts the session. |

#### Methods Details

##### <a name="arrays_all"></a> Method: `all()`

```php
/**
 * Gets all session values as array.
 *
 * @return array The session values
 */
public function all(): array
```

##### Example

```php
$result = $session->all();
```

##### <a name="arrays_close"></a> Method: `close()`

```php
/**
 * Force the session to be saved and closed.
 *
 * Session data is usually stored after your script terminated without the need
 * to call close(), but as session data is locked to prevent concurrent
 * writes only one script may operate on a session at any time. When using
 * framesets together with sessions you will experience the frames loading one
 * by one due to this locking. You can reduce the time needed to load all the
 * frames by ending the session as soon as all changes to session variables are
 * done.
 */
public function close(): void
```

##### Example

```php
$session->close();
```

##### <a name="arrays_setOptions"></a> Method: `setOptions()`

```php
/**
 * Set session runtime configuration.
 *
 * @see http://php.net/manual/en/session.configuration.php
 *
 * @param array $config The session options.
 */
public function setOptions(array $options): void
```

##### Example

```php
$session->setOptions([
    'use_cookies' => 1,
    'cookie_secure' => 1,
    'use_only_cookies' => 1,
    'cookie_httponly' => 1,
    'use_strict_mode' => 1,
    'sid_bits_per_character' => 5,
    'sid_length' => 48,
    'cache_limiter' => 'nocache',
    'cookie_samesite' => 'Lax'
]);
```

### Tests

Run tests

```
./vendor/bin/pest
```

### License
[The MIT License (MIT)](https://github.com/atomastic/session/blob/master/LICENSE.txt)
Copyright (c) 2020 [Sergey Romanenko](https://github.com/Awilum)
