---
title: "Vue LifeCycle"
date: 2023-05-05T08:06:25+06:00
menu:
  sidebar:
    name: "[前端] Vue LifeCycle"
    identifier: VueLifeCycle
    parent: Vue
    weight: 40
hero: boat.jpg
categories: ["Basic"]
---

### LifeCycle 生命週期 
每個 Vue 組件實例在創建時都會經歷一系列初始化步驟——例如，它需要設置數據觀察、編譯模板、將實例掛載到 DOM 以及在數據變化時更新 DOM。在此過程中，它還運行稱為生命週期掛鉤的功能，讓用戶有機會在特定階段添加自己的代碼。


### 生命週期完整圖
{{< img src="./images/life0.png" align="center" title="Forest">}}

### 實體建立階段

{{< img src="./images/life1.png" align="center" title="Forest">}}

|Vue 2.x/3.x   |Vue 3.0 Composition API| 說明 |
|:------:|:---:|:------:|
| beforeCreate | setup()  | Vue 實體被建立，狀態與事件都尚未初始化 |
| created      | setup()  | Vue 實體已建立，狀態與事件已初始化完成 (prop、data、computed 等屬性已建立，vm.$el 屬性無法使用 ) |
| beforeMount | onBeforeMonut  |  Vue 實體尚未與模板 (DOM 節點) 綁定   |                                 

### 實體更新階段

{{< img src="./images/life2.png" align="center" title="Forest">}}

|Vue 2.x/3.x   | Vue 3.0 Composition API| 說明 |
|:------:|:---:|:------:|
|mounted | onMounted  | Vue 實體與掛載完成， el 的目標 DOM 被 $el 所替換 (可以視作 jQuery 的 Ready) |
| beforeUpdate     | onBeforeUpdate  | 當狀態被變動時，畫面同步更新前 |
|updated | onUpdated  |  當狀態被變動時，畫面已同步更新完成   |  
### 實體銷毀階段

{{< img src="./images/life3.png" align="center" title="Forest">}}

|Vue 2.x/3.x   | Vue 3.0 Composition API| 說明 |
|:------:|:---:|:------:|
|beforeDestroy (2.x) | onBeforeUnmount  | Vue 實體物件被銷毀前 |
|beforeUnmount (3.0) | onBeforeUnmount  | Vue 實體物件被銷毀前 |
|destroyed (2.x) | onUnmounted  | Vue 實體物件被銷毀完畢 |
|unmounted (3.0) | onUnmounted  | Vue 實體物件被銷毀完畢 |

### 實體錯誤階段

|Vue 2.x/3.x   | Vue 3.0 Composition API| 說明 |
|:------:|:---:|:------:|
|errorCaptured |onErrorCaptured  | 子/孫代元件的錯誤被捕獲時觸發 |

### Composition Api VS Option Api
Vue Composition API 是 Vue.js 3.0 開始提供的新特性，Vue.js 3.0 針對多數 2.x 的語法提供了向下相容，所以Vue.js 2.x Options API 的生命週期 Hooks 到了 3.0 依然可以繼續使用。 Composition API 的 Hook 名稱除了 `beforeCreate` 與 created 由新的 `setup()` 所取代， 以及元件銷毀的 `beforeDestroy` 與 `destroyed` 改為 `onBeforeUnmount` 與 `onUnmounted` 之外， 多數都是在原有名稱加上 `on` 來表示。

建議3.0開始使用的人，一率都使用Composition Api

