
# Online-Order-Process-BPMN-diagram
Visual representation of the e-commerce order lifecycle using BPMN, built in Bizagi.

![Image](https://github.com/user-attachments/assets/59742c3f-f648-4e3b-893d-d180a0749557)

This project showcases a complete **Business Process Model and Notation (BPMN)** diagram built using **Bizagi Modeler**, representing the end-to-end workflow of the online order — from user placement to delivery.


## 📌 Project Objective

To model the process flow of an e-commerce order fulfillment system, covering every step from order initiation to successful delivery (or exception handling like payment failure or delivery failure). This diagram helps visualize process responsibilities, decisions, and outcomes.


## 🧰 Tools Used

- **Bizagi Modeler** (Free desktop application)
- **BPMN 2.0 Standard**


## 🧠 Key BPMN Concepts Used

- **Pools & Lanes** – to define participants (Customer, Platform, Warehouse, Courier)
- **Tasks** – for actions like placing order, payment processing, packaging
- **Gateways** – for decision points (e.g., Payment Success? Delivery Success?)
- **Events** – to define Start and End of the workflow
- **Documentation** – added to each element for clarity (visible in XPDL export)

---

## 🏗️ Process Structure

| **Pool**                  | **Lane**             | **Activities / Events / Gateways**                                      |
|---------------------------|----------------------|--------------------------------------------------------------------------|
| **Online Order Fulfillment** | **Customer**          | 🔵 **Start Event** – Customer initiates the process  <br> 🟦 **Task** – Customer places order from website/app <br> 🟦 **Task** – Receive Order Confirmation |
 |                         | **E-Commerce Platform** | 🟦 **Task** – System checks inventory stock <br> 🟦 **Task** – Send Order to Warehouse <br> 🟦 **Task** – Payment gateway processes transaction <br> ◆ **Gateway** – Payment Successful?  <br> 🟦 **Task** – Continue (if YES) <br> 🟦 **Task** – Send Payment Failure Notification (if NO) <br> 🔴 **End Event** – Order not Placed |
|                           | **Warehouse**         | 🟦 **Task** – Warehouse team packs item <br> 🟦 **Task** – Hand Over to Courier |
|                           | **Courier Service**    | 🟦 **Task** – Deliver Item <br> ◆ **Gateway** – Delivery Successful? <br> 🟦 **Task** – Successful Delivery <br> 🔴 **End Event** – Send Delivery Confirmation to Customer (if YES) <br> 🟦 **Task** – Delivery Failed (if NO) <br> 🟦 **Task** – Initiate Return Process <br> 🟦 **Task** – Send back the item to warehouse <br> 🔴 **End Event** – Pay back to the origin |


## 🔁 Workflow Overview

1. **Customer** places an order.
2. **E-Commerce Platform** checks availability and processes payment.
3. If **payment is successful**, the order goes to the **warehouse**.
4. The **warehouse** packs and ships the product via **courier**.
5. **Courier** attempts delivery.
  
    A. If successful → customer is notified → process ends.

    B. If failed → return process begins.
