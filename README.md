# Microsoft Naming

It's hard to keep a mental model of Microsoft's product renames. So I'm trying to document it in a series of graphs.

Rules:

1. These graphs are about the Product Name only. Integrations between products come and go, and that's a whole other repo waiting to be created.

## Defender


```mermaid
graph LR;

    O365ATP[Office 365 ATP] --> DfO365[Defender for Office 365];
    MSE[Microsoft Security Essentials] --> WDAV[Windows Defender Anti-virus] --> WDATP[Windows Defender ATP] --> MDATP[Microsoft Defender ATP] --> MDfE[Microsoft Defender for Endpoint];
    MSE --> SCEP[System Center Endpoint Protection];
    WATA[Windows Advanced Threat Analytics] --> AATP[Azure Advanced Threat Protection] --> MDfI[Microsoft Defender for Identity];
    WATA --> MATP[Microsoft Advanced Threat Protection];

    ASentinel[Azure Sentinel] --> Sentinel[Microsoft Sentinel];
    
    ASC[Azure Security Center] --> ADfS[Azure Defender for Servers] --> MDfC[Microsoft Defender for Cloud];
    ATPfSQL[Advanced Threat Protection for SQL] --> ADfSQL[Azure Defender for SQL] --> MDfC;
    
    MCAS[Microsoft Cloud App Security] --> MDfCA[Microsoft Defender for Cloud Apps];
    
    ASCfIoT[Azure Security Center for IoT] --> ADfIoT[Azure Defender for IoT] --> MDfIoT[Microsoft Defender for IoT];
    CyberX --> ADfIoT

```

## Dynamics

```mermaid
graph TD;

    AX[Dynamics AX];
    CRM[Dynamics CRM];
    GP[Dynamics GP];
    NAV[Dynamics NAV];
    SL[Dynamics SL];
    
    CRM --> D365CS[Dynamics 365 Customer Service];
    
    GPD[Great Plains Dynamics and eEnterprise]-->GP;  

    Navision-->NAV-->D365FOB[Dynamics 365 for Finance and Operations, Business Edition]-->D365BC[Dynamics 365 Business Central];
    
    Axapta-->AX4[AX 4.0]-->AX-->D365O[Dynamics 365 for Operations]-->D365FOE[Dynamics 365 for Finance and Operations, Enterprise Edition]-->D365FO[Dynamics 365 Finance and Operations]-->D365FSCM[Dynamics 365 Finance and Supply Chain Management];
    
    D365FSCM-->D365F[Dynamics 365 Finance];
    D365FSCM-->D365SCM[Dynamics 365 Supply Chain Management];
```

## Endpoint Management

```mermaid
graph TD;

    Intune --> MEM[Microsoft Endpoint Manager];
    SCCM[System Center Configuration Manager] --> MECM[Microsoft Endpoint Configuration Manager];
```

## Identity

```mermaid
graph TD;

    IIFP --> MIIS --> ILM --> FIM --> MIM;
```

