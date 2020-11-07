---
title: Title 23 NYCRR Part 500
description: Microsoft에서는 Azure, Office 365, Power BI가 23 NYCRR 500 요구 사항을 준수하는 데 도움이 되는 방법을 설명하는 가이드를 준비했습니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: fa76fefbeea2c8fc0226a85d5b12599839eba8ca
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920410"
---
# <a name="title-23-nycrr-part-500"></a>Title 23 NYCRR Part 500

## <a name="title-23-nycrr-part-500-overview"></a>Title 23 NYCRR Part 500 개요

In response to the significant and ever-increasing threats to the cybersecurity of information and financial systems, in 2017, the State of New York Department of Financial Services imposed a new set of cybersecurity requirements on financial institutions that are licensed or authorized to do business in the state. This regulation — Title 23 New York Codes, Rules, and Regulation Part 500: Cybersecurity Requirements for Financial Services Companies — is designed to protect customer data and the information technology systems of financial institutions such as state-chartered, private, and international banks, mortgage brokers, and insurance companies.

## <a name="microsoft-and-title-23-nycrr-part-500"></a>Microsoft 및 Title 23 NYCRR Part 500

Microsoft provides a comprehensive guide, [Microsoft Cloud Services: Supporting Compliance with NYDFS Cybersecurity Requirements](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides), for financial services regulated under Title 23 NYCRR Part 500. It explains in depth how Azure, Office 365, and Power BI cloud services support compliance with the requirements. Financial institutions that seek to operate in the global financial center of New York must meet them, so compliance is critical for many institutions.

이 참고 자료에 따라 Title 23 NYCRR Part 500: Microsoft 클라우드 서비스: [NYDFS 사이버 보안 요구 사항 규정 준수 지원](https://go.microsoft.com/fwlink/p/?linkid=2098969)을 준수하는 데 도움을 얻을 수 있습니다.

뉴욕 규정에는 각 재무 기관이 다음을 수행해야 합니다.

- **Develop and maintain a robust cybersecurity program** starting with an assessment of the institution’s specific risk profile and then designing a program that addresses them. The [Microsoft Cloud Financial Services Compliance Program](https://www.microsoft.com/download/confirmation.aspx?id=55332) was created to help financial services assess the risks of using Microsoft cloud services. It includes direct engagement with our engineers and corporate risk officers and access to our compliance and security experts.
- **Implement a comprehensive cybersecurity policy** that addresses information security, data governance and classification, access controls, business continuity, and the like. Microsoft offers guidance for developing this policy with in-depth information about our certifications and risk assessments; business continuity and disaster recovery metrics; and diagnostics for logging and auditing.
- 사이버 보안 프로그램을 관리하고 정책을 적용하기 위한 **CISO(최고 정보 보호 책임자)를 지정** 합니다. CISO 지원을 위해 Microsoft는 [Azure Defender](https://azure.microsoft.com/services/security-center/?v=17.23h), [Office 365 Advanced Threat Analytics](https://docs.microsoft.com/advanced-threat-analytics/), [Power BI Security](https://go.microsoft.com/fwlink/?LinkId=829185)을 통해 Microsoft 클라우드 배포에 대한 심층 사이버 보안 정보를 제공합니다.
- **Monitor and test the effectiveness of its cybersecurity program** : Microsoft provides information from audits of its cybersecurity practices that include continuous monitoring, periodic penetration testing, and vulnerability assessments. Customers can conduct their own tests without advance permission from Microsoft.
- **Maintain an audit trail.** Built-in audit functionalities of Azure, Office 365, and Power BI customers generate information that can be used to reconstruct financial transactions and develop audit trail information.
- **비공개 정보를 포함하는 정보 시스템에 대한 액세스 제한** : Azure, Office 365, Power BI는 각 서비스에 대한 기본 RBAC(역할 기반 액세스 제어) 프로세스, 모든 Microsoft 관리자의 엄격한 보안 및 액세스 요구 사항, 강화된 액세스 권한에 대한 모든 요청 감사를 제공하는지 평가합니다.
- **외부 개발 애플리케이션에 대한 보안을 평가하고 테스트하기 위한 절차 도입** : Visual Studio를 사용하는 개발자는 관리 코드에 대한 [보안 규칙](https://docs.microsoft.com/visualstudio/code-quality/security-rules-rule-set-for-managed-code)을 코드가 배포되기 전에 애플리케이션 사이버 보안 위협이 감지되고 완화되는지 확인할 수 있습니다.
- **Use periodic risk assessments to design and enhance cybersecurity programs** : For customers, Microsoft aggregates information about security threats, provides roadmaps of change management, and regularly updates information about subcontractors. Microsoft also regularly conducts risk assessments of its own services, the results of which are available to customers.
- **Use qualified personnel to manage cybersecurity risks and oversee cybersecurity functions** : Microsoft employs stringent procedures for our employee access to your customer data. If we hire subcontractors, we remain responsible for service delivery, and ensure that subcontractors fully comply with Microsoft privacy and security commitments, including requirements for handling sensitive data, background checks, and non-disclosure agreements.
- **타사 서비스 공급자가 제공하는 정보의 보안을 보장하는 정책 및 절차 구현** : Azure, Office 365 및 Power BI는 회사 네트워크에 대한 모든 인바운드 연결에 대해 다단계 인증을 사용할 수 있습니다. 외부 네트워크를 통한 전송에서 비공개 정보를 보호하고 rest에서 보호할 수 있는 암호화를 비롯한 제어를 구현합니다. [Microsoft Online Services 사용 약관](https://aka.ms/Online-Services-Terms)을 통해 보안 문제에 대한 고객 공지, 인시던트 조사 및 위험 완화를 제공합니다.
- **데이터 보존 및 삭제 정책과 절차 구현** : Azure, Office 365, Power BI에 저장된 고객 데이터를 언제든지 액세스하고 추출할 수 있습니다.
- **Monitor the activity of authorized users, detect unauthorized access, and offer regular cybersecurity awareness training to employees** : Azure, Office 365, and Power BI include outside-in monitoring to raise alerts about incidents, and extensive diagnostics for logging and auditing. [Microsoft Virtual Academy](https://mva.microsoft.com/) offers online training that covers the cybersecurity of Microsoft cloud services.
- **Develop plans to respond to and recover from cybersecurity incidents** : Microsoft helps you prepare for cybersecurity incidents using a defensive strategy to detect, predict, and prevent security breaches before they occur. When developing your own plans, you can draw on our incident management plan for responding to cybersecurity breaches.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure](https://aka.ms/AzureCompliance)
- Intune
- [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- 독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**어떤 기관이 이 규제의 적용을 받나요?**

뉴욕주 금융서비스국 [감독 대상](https://go.microsoft.com/fwlink/p/?linkid=2099374)에 문의하여 해당 기관에 이 규제가 적용되는지 여부를 확인하세요.

## <a name="resources"></a>리소스

- [주요 리소스](https://www.microsoft.com/trustcenter/compliance/NYCRR)
- [New York State Department of Financial Services 23 NYCRR 500: 재무 서비스 기업을 위한 사이버 보안 요구 사항](https://go.microsoft.com/fwlink/p/?linkid=2098976)
- [FAQ: 23 NYCRR Part 500 – 사이버 보안](https://go.microsoft.com/fwlink/p/?linkid=2098977)
- [Microsoft 클라우드 서비스: NYDFS 사이버 보안 요구 사항 규정 준수 지원](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- [Microsoft 보안 센터의 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="other-microsoft-resources-for-financial-services"></a>금융 서비스에 대한 기타 Microsoft 리소스

- [Microsoft 비즈니스 클라우드 서비스 및 금융 서비스](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Microsoft 클라우드 금융 서비스 규정 준수 프로그램](https://www.microsoft.com/download/confirmation.aspx?id=55332)
- [Azure에서의 금융 서비스 규정 준수](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [클라우드 컴퓨팅에 대한 공동 책임](https://aka.ms/sharedresponsibility)- 
