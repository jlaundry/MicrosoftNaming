# Microsoft Naming

It's hard to keep a mental model of Microsoft's product renames. So I'm trying to document it in a series of graphs.

Rules:

1. These graphs are about the Product Name only. Integrations between products come and go, and that's a whole other repo waiting to be created.

## Core Suite

```mermaid
gantt
dateFormat  YYYY-MM
title Core Suite
excludes weekdays 2010-01-01

section Identity
Azure AD                                  :done,   aad,     2013-04, 2021-11
Entra ID                                  :active, entraid, 2023-08, 2023-12

section Productivity
Office 365                                :done,   o365,    2010-10, 2022-11
Microsoft 365 (consumer)                  :done,   m365c,   2020-04, 2022-11
Microsoft 365                             :active, m365,    2022-11, 2023-12
```

Sources:
  * https://weblogs.asp.net/scottgu/windows-azure-active-directory-general-availability-new-backup-service-web-site-monitoring-and-diagnostic-improvements
  * https://techcommunity.microsoft.com/t5/microsoft-entra-azure-ad-blog/azure-ad-is-becoming-microsoft-entra-id/ba-p/2520436

## Defender


```mermaid
graph LR;

    FOPE[Forefront Online Protection for Exchange] --> EOP[Exchange Online Protection];
    O365ATP[Office 365 ATP] --> DfO365[Defender for Office 365];
    
    MSE[Microsoft Security Essentials] --> WDAV[Windows Defender Anti-virus] --> WDATP[Windows Defender ATP] --> MDATP[Microsoft Defender ATP] --> MDfE[Microsoft Defender for Endpoint];
    MSE --> MFEP[Microsoft Forefront Endpoint Protection] --> SCEP[System Center Endpoint Protection];
    WATA[Windows Advanced Threat Analytics] --> AATP[Azure Advanced Threat Protection] --> MDfI[Microsoft Defender for Identity];
    WATA --> MATP[Microsoft Advanced Threat Protection];

    ASentinel[Azure Sentinel] --> Sentinel[Microsoft Sentinel];
    
    ASC[Azure Security Center] --> ADfS[Azure Defender for Servers] --> MDfC[Microsoft Defender for Cloud];
    ATPfSQL[Advanced Threat Protection for SQL] --> ADfSQL[Azure Defender for SQL] --> MDfC;
    
    Adallom --> MCAS[Microsoft Cloud App Security];
    MCAS --> MDfCA[Microsoft Defender for Cloud Apps];
    
    ASCfIoT[Azure Security Center for IoT] --> ADfIoT[Azure Defender for IoT] --> MDfIoT[Microsoft Defender for IoT];
    CyberX --> ADfIoT
    
    RiskIQ --> MDTI[Microsoft Defender Threat Intelligence];
    RiskIQ --> MDEASM[Microsoft Defender External Attack Surface Management];
    

```

```mermaid
gantt
dateFormat  YYYY-MM
title Microsoft Security products
excludes weekdays 2010-01-01

section SIEM
Azure Sentinel                            :done,   asentinel, 2019-09, 2021-11
Microsoft Sentinel                        :active, msentinel, 2021-11, 2023-12

section CASB
Adallom                                   :done,     adallom, 2013-11, 2016-04
Microsoft Cloud App Security (MCAS)       :done,        mcas, 2016-04, 2021-11
Microsoft Defender for Cloud Apps (MDfCA) :active,     mdfca, 2021-11, 2023-12

section Server Workload
Azure Security Center (ASC)               :done,         asc, 2016-07, 2021-11
Azure Defender                            :done,      azured, 2016-07, 2021-11
Microsoft Defender for Cloud (MDfC)       :active,      mdfc, 2021-11, 2023-12

section Identity
Windows Advanced Threat Analytics (WATA)  :done,        wata, 2016-05, 2021-01
Azure Advanced Threat Protection (AATP)   :done,        aatp, 2018-03, 2020-11
Microsoft Defender for Identity (MDfI)    :active,      mdfi, 2020-11, 2023-12

section Email
Forefront Online Protection for Exchange (FOPE)  :done,      fope, 2011-04, 2013-11
Exchange Online Protection (EOP)                 :active,     eop, 2013-11, 2024-01
Office 365 ATP (O365ATP)                         :done,   o365atp, 2018-03, 2020-09
Microsoft Defender for Office 365 (MDfO365)      :active,    mdfi, 2020-09, 2023-12

section TI
RiskIQ                                                 :active, riskiq, 2012-01, 2022-08
Microsoft Defender Threat Intelligence                 :active,   mdti, 2022-08, 2023-12
Microsoft Defender External Attack Surface Management  :active, mdeasm, 2022-08, 2023-12

```

## Dynamics

```mermaid
graph TD;

    AX[Dynamics AX];
    CRM[Dynamics CRM];
    GP[Dynamics GP];
    NAV[Dynamics NAV];
    SL[Dynamics SL];
    
    CRM --> D365CE[Dynamics 365 Customer Engagement];
    
    GPD[Great Plains Dynamics and eEnterprise]-->GP;  

    Navision-->NAV-->D365FOB[Dynamics 365 for Finance and Operations, Business Edition]-->D365BC[Dynamics 365 Business Central];
    
    Axapta-->AX4[AX 4.0]-->AX-->D365O[Dynamics 365 for Operations]-->D365FOE[Dynamics 365 for Finance and Operations, Enterprise Edition]-->D365FO[Dynamics 365 Finance and Operations]-->D365FSCM[Dynamics 365 Finance and Supply Chain Management];
    
    D365FSCM-->D365F[Dynamics 365 Finance];
    D365FSCM-->D365SCM[Dynamics 365 Supply Chain Management];
```

## Endpoint Management

```mermaid
graph TD;

    Intune --> MEM[Microsoft Endpoint Manager] --> Intune;
    SCCM[System Center Configuration Manager] --> MECM[Microsoft Endpoint Configuration Manager]  --> MCM[Microsoft Configuration Manager];
```

## Identity

```mermaid
graph TD;

    IIFP --> MIIS --> ILM --> FIM --> MIM;
```

