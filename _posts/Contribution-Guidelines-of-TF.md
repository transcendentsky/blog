---
title: 开源项目注意事项 \n（Contribution Guidelines of TF）
date: 2018-07-05 19:33:49
tags: mess
---
### 总结
- 涉及版权等问题需要许可，要注意
- unit test十分重要，对代码维护和版本兼容
- License
- 代码风格保持以及代码风格维护工具

Guidelines
Code of Conduct
签署CLA协议（github中）
检查修改是否和guidelines一致
检查编码风格是否一致
能否运行单元检测（Unit Tests）


### Contributor License Agreements
如果是个人写代码，请确保你拥有这个知识产权，并签署个人CLA协议
如果你是员工，你需要签署公司CLA协议
签署协议后我们才能接受你的pull request

### Contributing Code
你贡献的代码不会第一时间放到主代码中，看情况会作为patch发布
如果你想贡献却没有方向， 你可以看xxx ，

### Contribution guidelines and Standards
Guidelines
- 贡献新特性确保有一个unit test，保证其正确性以及以后代码的兼容性
- 修复bugs也要有unit test，
- 请保持API的兼容性
- 当你贡献新特性后，维护工作会交给tf团队，这意味着其作用需要大于维护成本

License：
新文件 顶部需要有 license

Python 代码风格：
使用pylint确认你的代码 （c/c++ 使用 clang-tidy）

运行unit tests。。。。


```
# Copyright 2015 The TensorFlow Authors. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# =============================================================================
位于代码顶部
```