# PD\Cache

> PD\Cache 是一個 PHP 混合式快取系統，結合了 Redis 和檔案系統快取，並具有檔案系統自動備用支援。

![tag](https://img.shields.io/badge/tag-PHP%20Library-bb4444)
![size](https://img.shields.io/github/size/pardnchiu/PHP-Cache/src/Cache.php)  
![version](https://img.shields.io/packagist/v/pardnchiu/cache)
![download](https://img.shields.io/packagist/dm/pardnchiu/cache)

## 特色功能

- 混合式快取策略（Redis + 檔案系統）
- Redis 無法使用時自動切換至檔案系統
- 內建 HTML / 文字內容最佳化
- 自動快取過期處理
- 快取清理機制
- MD5 快取鍵值產生

## 核心功能

- 自動選擇儲存方式的快取讀寫
- HTML/文字內容最小化
- 自動快取過期
- 過期項目快取清理
- 系統彈性備用機制

## 相依套件

- `pardnchiu/redis` - Redis 快取支援（選用）
- `/storage/caches` - 儲存目錄需要寫入權限

## 使用方式

### 安裝

```shell
composer require pardnchiu/cache
```

```php
// 使用 Redis 支援進行初始化
$redis = new PD\Redis();
$cache = new PD\Cache($redis);

// 設定 1 小時過期的快取
$cache->set("page-key", $content, 3600);

// 取得快取內容
$content = $cache->get("page-key");

// 清理過期的快取項目
$cache->clean();

// 不使用 Redis 初始化（僅檔案系統）
$cache = new PD\Cache();
```

## 授權條款

此原始碼專案採用 [MIT](https://github.com/pardnchiu/PHP-Cache/blob/main/LICENSE) 授權。

## 作者

<img src="https://avatars.githubusercontent.com/u/25631760" align="left" width="96" height="96" style="margin-right: 0.5rem;">

#### 邱敬幃 Pardn Chiu

<a href="mailto:dev@pardn.io" target="_blank">
 <img src="https://pardn.io/image/email.svg" width="48" height="48">
</a>
<a href="https://linkedin.com/in/pardnchiu" target="_blank">
 <img src="https://pardn.io/image/linkedin.svg" width="48" height="48">
</a>

---

©️ 2024 [邱敬幃 Pardn Chiu](https://pardn.io)