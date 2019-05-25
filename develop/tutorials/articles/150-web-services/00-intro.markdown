---
header-id: web-services
---

# Web Services

[TOC levels=1-4]

It's important for apps on different machines to communicate. To enable this, an
app can expose APIs so remote components (other apps or devices) can access the
app's features. For example, one service could have a client app presenting
information to users, a server app processing data in B2B setting, and an IoT
device requesting data to do its work. Exposing web APIs lets external
applications or devices communicate with yours. 

Because @product@ contains so many apps and features, it's prudent for Liferay
to let developers access those apps and features from external apps and devices
by exposing their APIs. Additionally, Liferay's development platform makes it
easy to extend them and create new ones. 

| **Note:** Hypermedia REST APIs are currently available in beta. To use them, you
| must be running Liferay CE Portal 7.1 GA3+, or Liferay DXP 7.1 Fix Pack 5+. You
| must also
| [enable the APIs](/docs/7-1/tutorials/-/knowledge_base/t/enabling-hypermedia-rest-apis)
| prior to use.

There are two different approaches for clients to connect to @product@'s web 
APIs: 

-   **Hypermedia REST APIs (beta):** These services are designed and built in an 
    opinionated way, and thus decoupled from the internal model. They follow 
    well-known industry standards and allow evolution of the APIs without 
    breaking clients. This is the modern, preferred way to work with web 
    services in @product@. 

-   **Plain Web/REST Services:** This is the old way to build and consume web 
    services in @product@, but is still supported. For example, you can use 
    [JAX-RS](/docs/7-1/tutorials/-/knowledge_base/t/jax-rs), 
    [JAX-WS](/docs/7-1/tutorials/-/knowledge_base/t/jax-ws), 
    or 
    [Service Builder](/docs/7-1/tutorials/-/knowledge_base/t/service-builder-web-services) 
    to implement plain REST or SOAP web services. 

The tutorials that follow show you how to consume and create web services in 
@product@, beginning with hypermedia REST APIs. 
