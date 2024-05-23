# Nội dung ngày 1:
## 1. Hướng dẫn các thông tin cơ bản về extension.
Extension được cấu thành cơ bản từ 3 thành phần chính:

- File content script.
Content script là các tệp JavaScript chạy trong ngữ cảnh của các trang web mà extension của bạn có quyền truy cập. Những tệp này cho phép extension tương tác và thay đổi nội dung của trang web.
- File background.
là một tập lệnh chạy ngầm trong nền của extension và không tương tác trực tiếp với các trang web. Nó có thể thực hiện các tác vụ dài hạn, quản lý trạng thái, và xử lý các sự kiện mà không yêu cầu sự hiện diện của người dùng. Background script thường được sử dụng để quản lý các chức năng như lưu trữ dữ liệu, xử lý các sự kiện, và giao tiếp với content scripts hoặc popup scripts.

- Các trang html (bao gồm các file cấu thành như html, js, css)

## 2. Giải thích các phần cơ bản của file manifest.
````
{
  "manifest_version": 3,
  "name": "My Simple Extension",
  "version": "1.0",
  "description": "A simple example of a browser extension",
  "permissions": [
    "activeTab",
    "storage"
  ],
  "background": {
    "service_worker": "background.js"
  },
  "content_scripts": [
    {
      "matches": ["<all_urls>"],
      "js": ["content.js"]
    }
  ],
  "action": {
    "default_popup": "popup.html",
    "default_icon": {
      "16": "images/icon16.png",
      "48": "images/icon48.png",
      "128": "images/icon128.png"
    }
  },
  "icons": {
    "16": "images/icon16.png",
    "48": "images/icon48.png",
    "128": "images/icon128.png"
  }
}
````