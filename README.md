# PD\Cache

> PD\Cache is a hybrid caching system for PHP that combines Redis and filesystem caching with automatic fallback support. Provides seamless caching capabilities even when Redis is unavailable.

![tag](https://img.shields.io/badge/tag-PHP%20Library-bb4444) 
![size](https://img.shields.io/github/size/pardnchiu/PHP-Cache/src/SQL.php)<br>
![version](https://img.shields.io/packagist/v/pardnchiu/cache)
![download](https://img.shields.io/packagist/dm/pardnchiu/cache)

## Features

- Hybrid caching strategy (Redis + Filesystem)
- Automatic fallback to filesystem when Redis is unavailable
- Built-in content optimization for HTML/Text content
- Automatic cache expiration handling
- Cache cleanup mechanism
- MD5 key generation for cache entries

## Key Capabilities

- Get/Set cache with automatic storage selection
- Content minification for HTML/Text
- Automatic cache expiration
- Cache cleanup for expired entries
- Fallback mechanism for system resilience

## Dependencies

- `pardnchiu/redis` - For Redis caching support (optional)
- `/storage/caches` - Write permission on storage directory 

## How to Use

### Install

```SHELL
composer require pardnchiu/cache
```

```PHP
// Initialize cache with Redis support
$redis = new PD\Redis();
$cache = new PD\Cache($redis);

// Set cache with 1-hour expiration
$cache->set("page-key", $content, 3600);

// Get cached content
$content = $cache->get("page-key");

// Clean expired cache entries
$cache->clean();

// Initialize cache without Redis (filesystem only)
$cache = new PD\Cache();
```

## License

This source code project is licensed under the [MIT](https://github.com/pardnchiu/PHP-Cache/blob/main/LICENSE) license.

## Creator

<img src="https://avatars.githubusercontent.com/u/25631760" align="left" width="96" height="96" style="margin-right: 0.5rem;">

<h4 style="padding-top: 0">邱敬幃 Pardn Chiu</h4>

<a href="mailto:dev@pardn.io" target="_blank">
    <img src="https://pardn.io/image/email.svg" width="48" height="48">
</a> <a href="https://linkedin.com/in/pardnchiu" target="_blank">
    <img src="https://pardn.io/image/linkedin.svg" width="48" height="48">
</a>

***

©️ 2024 [邱敬幃 Pardn Chiu](https://pardn.io)