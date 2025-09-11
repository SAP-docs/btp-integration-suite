<!-- loio26a9db10dbf44a768163a7b14ce8d763 -->

# Reusable API Artifact

Reusable APIs provide modular, internal-only components that encapsulate shared policies like authentication, transformation, and validation. Centrally managed and invoked by calling APIs \(i.e., the API artifact that consume the reusable API artifact\) via the API Direct adapter, they reduce duplication, enforce consistency, and maintain independent lifecycles for better scalability and governance.

Reusable API artifacts are designed to be used internally as building blocks for complex workflows. They do not have their own endpoints and are not meant to be exposed externally.

Reusable APIs enforce authentication policy coverage across the complete execution chain, though individual artifacts may not require it. Each reusable API must have a unique basepath, and interactions between the calling API artifacts \(i.e., the API artifact that consume the reusable API artifact\) and reusable APIs are optimized to minimize latency and maintain traceability via shared correlation IDs. By decoupling their lifecycle from calling APIs, reusable artifacts allow greater flexibility in governance, monitoring, and deployment strategies—making them an essential tool in scalable API architecture within Edge Integration Cell.

**Related Information**  


[Create a Reusable API Artifact](create-a-reusable-api-artifact-0112688.md "A reusable API artifact is created so that its components and services can be leveraged repeatedly across various applications, projects, or contexts without needing substantial rewrites or modifications.")

[Consuming a Reusable API Artifact](consuming-a-reusable-api-artifact-291f424.md "Consuming reusable API artifacts significantly improves the consistency, efficiency, and maintainability of API development. By leveraging predefined components such as policies, mediation steps, and configurations, teams can ensure standardized behavior across APIs, reduce duplication, and simplify updates.")

