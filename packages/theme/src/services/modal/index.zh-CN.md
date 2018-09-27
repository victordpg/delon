---
order: 3
title: 对话框辅助类
type: Service
---

基于 `NzModalService` 封装，它解决一些已知问题：

- 更友好的处理回调
- 自动管理 `z-index` 值

## 用法

```ts
this.modalHelper.create(FormEditComponent, { i }).subscribe(res => this.load());

// 成功范例
// 1. 视为成功
this.subject.close(true);
this.subject.close({ other: 1 });
// 2. 视为失败
this.subject.close();

// 关闭：
this.subject.destroy();
```

包括两个方法体 `create` & `createStatic` 分别打开普通&静态对话框。在 `NzModalService` 基础上新增若干参数。

### API

| 名称 | 类型 | 默认值 | 描述 |
| --- | --- | --- | --- |
| `size` | `sm,md,lg,xl,number` | `lg` | 指定对话框大小 |
| `exact` | `boolean` | `true` | 是否精准（默认：`true`），若返回值非空值（`null`或`undefined`）视为成功，否则视为错误 |
| `includeTabs` | `boolean` | `false` | 是否包裹标签页 |
| `modalOptions` | `ModalOptionsForService` | - | nz-modal 对话框原始参数 |