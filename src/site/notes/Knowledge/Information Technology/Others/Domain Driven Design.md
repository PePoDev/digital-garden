---
{"dg-publish":true,"permalink":"/knowledge/information-technology/others/domain-driven-design/","dgPassFrontmatter":true}
---

# Problem Space vs Solution Space
![Pasted image 20230219223400.png](/img/user/Attachments/Pasted%20image%2020230219223400.png)
![Attachments/Pasted image 20230313171248.png](/img/user/Attachments/Pasted%20image%2020230313171248.png)

## Domains
- Core domains
- Generic domains
- Supporting domains

![Attachments/Pasted image 20230313171831.png](/img/user/Attachments/Pasted%20image%2020230313171831.png)

## Integrating Bounded Context
-   Partnership — ต่อกันแบบ Ad hoc 1–1
-   Shared Kernel — ใช้ Database ร่วมกัน
-   Conformist — คนที่จะมาต่อต้องยอมทำตาม Spec ของ Service Providers
-   Filter — คนที่จะมาต่อต้องกรองเอาเองว่าจะใช้ข้อมูลตัวไหนบ้าง
-   Open-host service — Open API concept
-   Separate way — ต่างฝ่ายต่างมองไม่เห็นกัน และมีตัวกลางบางอย่างคอยเป็นคนสื่อสารให้
