# 软件需求变更单

**Software scope change worksheet · 简体中文 / English**

客户说「发货前可以改地址」，开发团队听到的可能是「生成面单前可以改地址」。包裹已经贴了面单，却还没交给快递员时，这两句话会产生不同的结果。用下面这张表把分歧说清楚，再决定这一版怎么做。

A client asks to edit an address “before shipping.” The engineer hears “before a shipping label exists.” Both interpretations work until a parcel sits on the packing bench with its label attached. Use the worksheet to decide what should happen to that parcel.

## 复制填写 / Copy and fill in

每次只填一项变更。把验收方法写成另一位同事可以照做的步骤。

Use one copy per change. Write a check that a teammate could perform.

| 项目 / Field | 双方填写 / Working notes |
| --- | --- |
| 目前约定的版本怎么运行？ / What does the agreed version do today? | |
| 想改什么，谁会用？ / What should change, and for whom? | |
| 哪些情况下适用，哪些情况下不适用？ / When does the new behavior apply, and when should it stop? | |
| 怎么测试，应该看到什么结果？ / What will we try, and what should we see? | |
| 哪些事情这次不做？ / What stays out of scope? | |
| 费用和日期有何变化？谁来核实待确认事项？ / What changes in cost or timing? Who will check any unknowns? | |
| 本次纳入、替换另一项、暂缓，还是不采纳？ / Include now, swap out another item, defer, or decline? | |
| 谁在何时批准了哪个版本？ / Who approved which version, and when? | |

## 填写示例 / Worked example

**场景（虚构）**　商店后台目前只能查看收货地址。客服希望改正门牌号，需求写的是「发货前可改」。团队建议只允许在生成面单前修改地址。面单采用最近一次成功保存的地址，面单一旦生成，该地址就被锁定。作废和重打面单留到以后讨论。

**验收**　找一笔还没有生成面单的测试订单，把门牌号从 18 改成 81，保存，再生成面单。重新打开订单，核对订单和面单，两处都应显示 81。另找一笔还没有生成面单、门牌号为 18 的测试订单，打开编辑页，让同事先生成面单，然后再保存 81。这次应提示地址已锁定。重新打开订单时，地址和面单都应显示 18。

**决定**　暂缓。工程负责人先确认系统何时得知面单已生成，并估算改动。产品负责人看到费用和日期的影响后，再决定是否纳入本次发布。此时表里还没有批准日期。

**Scenario (fictional)**　The shop’s order screen currently shows a read-only address. Customer support wants to correct a house number “before shipping.” The team proposes a narrower rule. Staff can edit an address until a label has been created. The label uses the last address saved successfully. Once the label exists, that address is locked. Voiding and reprinting labels are outside this change.

**Acceptance check**　Start with a test order that has no label. Change house number 18 to 81, save, and then create the label. Reopen the order. Both the order and the label should show 81. Open the editor on a second unlabeled order for number 18. Have a colleague create the label before you save 81. Expect a message that the address is locked. On reopening, both the order and its label should still show 18.

**Decision**　Deferred. The engineering lead will check when the system learns that a label exists and estimate the work. The product owner will decide whether to include it in this release once the cost and schedule effects are known. The approval date is still blank.

由 Edward Amirain 创立的 Vaynerov Technologies 发布，使用 AI 辅助编写。

Published by Vaynerov Technologies, founded by Edward Amirain. Prepared with AI assistance.

[工作室的工程协作指南（英文） / Studio guide to engineering collaboration](https://vaynerov.com/services/engineering-partners) · [项目简报表（英文） / Project brief worksheet](https://vaynerov.com/resources/project-brief.html)
