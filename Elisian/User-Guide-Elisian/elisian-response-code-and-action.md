---
title: "Response Code dan Action Elisian"
date: "2020-03-24"
document type: "2"
author: "Farida Nur Hidayah"
summary: "Informasi rilis dan update Elisian"
---

# **Response Code (RC) dan Action**

> Daftar definisi kode respon beserta aksi tindaklanjut yang direkomendasikan.

|**Status**| **RC** |**Message**| **Description** | **Recommended Action** |
| -------| ------ | ------------| --------------| ------------------------ |
| Success | 0 | *different per product type | Success Transaction | - |
| Pending | 10 | Pending | Pending Transaction | Escalate to Alterra if more than 10 min|
| Cancel  | 98 | Cancelled | Order Canceled by Alterra (Suspected Transaction)|Advice Customer to redo transaction, and escalate to Alterra if repeated more than 5 times|
| Failed | 20 | Number Expired | Customer Number is Expired | Advice Customer to check their Number |
| Failed | 20 | Number Blocked | Customer Number is Blocked from Supplier | Advice Customer to escalate to Supplier / Telco | 
| Failed | 20 | Wrong Number / Number Blocked / Number Expired | Customer Number either is Wrong / Blocked / Expired (unseparated RC from supplier) | Advice Customer to check their Number first, then redo transaction |
| Failed | 21 | Product Issue | Product Issue from Alterra / Supplier | Advice Customer to redo transaction, and escalate to Alterra if repeated more than 5 times |
| Failed | 22 | Duplicate Transaction | Limited Transaction from Supplier for Same Number | Advice Customer to check their quota / redo transaction day after |
| Failed | 23 | Connection Timeout | Connection Issue from Supplier |Advice Customer to redo transaction, and escalate to Alterra if repeated more than 5 times |
| Failed | 24 | Product Cut Off | Product Cut Off dari Supplier | Escalate to Alterra to know how long the cut off will be, and advice customer to redo transaction after |
| Failed | 25 | Payment / Kwh Amount is Overlimit | Kwh Overlimit for Electricity or Payment Overlimit for Other Products | Advice customer to check the quota of their kwh / payment amount |
| Failed | 26 | Inquiry: Payment Amount is Over Limit | Bill Payment is blocked by Alterra because of Amount Limitation | Escalate to Alterra |
| Failed | 50 | Bill already paid / not yet available | Bill Payment is paid or not yet available for this month | Advice Customer to check their bills due and redo transaction after |
| Failed | 51 | Invalid Inquiry | Inquiry Problem | Advice Customer to redo transaction, and escalate to Alterra if repeated more than 5 times |
| Failed | 51 | Invalid Payment | Payment Problem (Invalid Amount) | Advice Customer to redo transaction, and escalate to Alterra if repeated more than 5 times |
| Failed | 99 | Maximum Transaction Capacity | Maximum Transaction Capacity from Supplier | Set Queueing Transaction and Escalate to Alterra |
| Failed | 99 | Failed after Recon with Biller | Updated transaction from suspected transaction| Escalate to Alterra if the latency for this transaction is more than 2 days |
| Failed | 99 | General Error | PUnidentified Message from Supplier | Advice Customer to redo transaction, and escalate to Alterra if repeated more than 5 times |