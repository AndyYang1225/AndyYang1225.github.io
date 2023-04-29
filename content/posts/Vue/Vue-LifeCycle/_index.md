---
title: "Vue LifeCycle"
menu:
  sidebar:
    name: "[前端] Vue LifeCycle"
    identifier: VueLifeCycle
    parent: Vue
    weight: 40
hero: boat.jpg
---


### LifeCycle 生命週期 
每個 Vue 組件實例在創建時都會經歷一系列初始化步驟——例如，它需要設置數據觀察、編譯模板、將實例掛載到 DOM 以及在數據變化時更新 DOM。在此過程中，它還運行稱為生命週期掛鉤的功能，讓用戶有機會在特定階段添加自己的代碼。

{{< img src="content/posts/Vue/Vue-LifeCycle\images/lifecycle.png" align="center" title="Forest">}}