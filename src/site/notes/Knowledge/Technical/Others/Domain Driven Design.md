---
{"dg-publish":true,"permalink":"/knowledge/technical/others/domain-driven-design/","dgPassFrontmatter":true}
---

# Problem Space vs Solution Space
![Domain Driven Design-2023-04-26.png](/img/user/Attachments/Domain%20Driven%20Design-2023-04-26.png)
![Domain Driven Design-2023-04-26-1.png](/img/user/Attachments/Domain%20Driven%20Design-2023-04-26-1.png)

## Domains
- Core domains
- Generic domains
- Supporting domains

![Domain Driven Design-2023-04-26-2.png](/img/user/Attachments/Domain%20Driven%20Design-2023-04-26-2.png)

## Integrating Bounded Context
-   Partnership — ต่อกันแบบ Ad hoc 1–1
-   Shared Kernel — ใช้ Database ร่วมกัน
-   Conformist — คนที่จะมาต่อต้องยอมทำตาม Spec ของ Service Providers
-   Filter — คนที่จะมาต่อต้องกรองเอาเองว่าจะใช้ข้อมูลตัวไหนบ้าง
-   Open-host service — Open API concept
-   Separate way — ต่างฝ่ายต่างมองไม่เห็นกัน และมีตัวกลางบางอย่างคอยเป็นคนสื่อสารให้
