# Taxonomy of DCM

This taxonomy of DCM achieves three key goals. First, it defines the top-level domains that distinguish  the functions and roles of the DCM architecture. Next, it defines a specific vocabulary with the intent of enabling precision and clarity by eliminating ambiguity. Finally, an "anti-vocabulary" defines a list of ambiguous phrases and "weasel words" to avoid and recommends more specific terms to use instead.

## Top-level architectural domains

The taxonomy defines the functional areas enabled by the DCM architectural as five top-level domains. Each domain maps a set of DCM services and resources defined by the architecture to the different roles and teams across an organization that experience them.

The top-level domains are defined as follows:

1. **Developer Experience** - This domain focuses on the unified interface that developers and application owners use to interact with DCM. It includes the self-service catalog, templates, and all user-facing documentation. This is where the DCM abstractions are consumed. Multi-tenancy is experienced at this level.
2. **Control Plane** - This is the central nervous system of DCM. It provides the unified API and maintains the DCM data model including the inventory of resources. It also enforces authentication and role-based access control.
3. **Orchestration & Automation** - This domain contains the code and workflows for provisioning and managing resources. It provides the engines that execute commands from the control plane to interact with the underlying Composable Infrastructure.
4. **Composable Infrastructure** - This domain represents the physical and virtual assets in the data center. It includes the compute, storage, and networking resources that are managed by the automation domain.
5. **Governance & FinOps** - This domain is a set of overarching requirements that ensure that DCM operations are secure, compliant, and cost-effective. It encompasses policy management, real-time metrics, and cost allocation.

Everything in the DCM architecture exists under one of these domains. 

How these domains are connected can be easily understood using a layer cake analogy. 

![Layer cake analogy drawing described below](./images/layer_cake.png)

Each layer of cake represents a domain that interacts only with the domains directly above and below it. For example, the architecture prohibits a direct connection from the Developer Experience domain to the Orchestration & Automation domain, Instead, Developer Experience must always use the Control Plane to request and manage resources available from the lower domains.

The exception to this rule is the Governance & FinOps domain. It is the frosting of our cake and it touches all the layers. This aligns with the overarching functions of the Governance & FinOps domain requiring observability at every level of the architecture. 
