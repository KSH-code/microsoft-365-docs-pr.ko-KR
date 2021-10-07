---
title: Microsoft Dynamics 365에서 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Microsoft에서 암호화 기술을 사용하여 Microsoft 데이터베이스에 저장되어 있는 동안 및 전송 중일 때 Microsoft Dynamics 365의 고객 데이터를 보호하는 방법을 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6fc07bba7ceccdfd2b215e29ef48dbd1f23c0cdf
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206076"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365에서 암호화

Microsoft는 Microsoft 데이터베이스에 저장되어 있으며 사용자 장치와 데이터 센터 간에 전송되는 동안에는 암호화 기술을 사용하여 Dynamics 365의 고객 데이터를 보호합니다. 고객과 Microsoft 데이터 센터 간에 설정되는 연결은 암호화되며 모든 공용 끝점은 업계 표준 TLS를 사용하여 보호됩니다. TLS는 보안이 강화된 브라우저 간 연결을 효과적으로 설정하여 데스크톱과 데이터 센터 간의 데이터 기밀성 및 무결성을 보장합니다. 데이터 암호화가 활성화된 후 해제할 수 없습니다. 자세한 내용은 필드 수준 데이터 [암호화를 참조하세요.](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8))

Dynamics 365는 표준 Microsoft SQL Server 수준 암호화를 사용하여 사용자 이름 및 전자 메일 암호와 같은 중요한 정보를 포함하는 기본 엔터티 특성 집합에 사용합니다. 이 기능은 조직이 FIPS 140-2와 관련된 규정 준수 요구 사항을 충족하는 데 도움이 될 수 있습니다. 필드 수준 데이터 암호화는 Dynamics 365 [인스턴스와 전자 메일](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8))서비스 간의 통합을 Microsoft Dynamics CRM 사용자 이름과 암호를 저장해야 하는 전자 메일 라우터를 활용하는 시나리오에서 특히 중요합니다.

Dynamics 365의 모든 [](/sql/relational-databases/security/encryption/transparent-data-encryption) 인스턴스는 TDE(Microsoft SQL Server 투명한 데이터 암호화)를 사용하여 디스크에 기록할 때(미사용) 데이터의 실시간 암호화를 수행합니다. TDE는 데이터 SQL Server, Azure SQL Database 및 Azure SQL 웨어하우스 데이터 파일을 암호화합니다. 기본적으로 Microsoft는 Dynamics 365 인스턴스에 대한 데이터베이스 암호화 키를 저장하고 관리합니다. Dynamics 365 for Financials에서 사용되는 키는 데이터 보호 API의 .NET Framework 생성됩니다.

Dynamics 365 관리 센터의 키 관리 기능을 사용하면 관리자는 Dynamics 365 인스턴스와 연결된 데이터베이스 암호화 키를 자체 관리할 수 있습니다. 자체 관리 데이터베이스 암호화 키는 Microsoft Dynamics 365용 2017년 1월 업데이트에서만 사용할 수 있으며 이후 버전에서는 사용할 수 없습니다. 자세한 내용은 [Dynamics 365(온라인)](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)인스턴스의 암호화 키 관리를 참조하세요. 키 관리 기능은 HSM에 저장된 키와 같은 PFX 및 BYOK 암호화 키 파일을 모두 지원합니다. (인터넷을 통해 HSM으로 보호된 키를 생성하고 전송하는 방법에 대한 자세한 내용은 [Azure Key Vault에 대한 HSM](/azure/key-vault/key-vault-hsm-protected-keys)보호 키를 생성하고 전송하는 방법을 참조하세요.)

암호화 키 업로드 옵션을 사용하려면 공개 및 개인 암호화 키가 모두 필요합니다.

키 관리 기능은 Azure Key Vault를 사용하여 암호화 키를 안전하게 저장하여 암호화 키 관리를 복잡하게 합니다. Azure Key Vault는 클라우드 응용 프로그램 및 서비스에서 사용하는 암호화 키와 암호를 보호하는 데 도움이 됩니다. 키 관리 기능을 사용하려면 Azure Key Vault 구독이 필요하지 않습니다. 대부분의 경우 자격 증명 모음 내에서 Dynamics 365에 사용되는 암호화 키에 액세스할 필요가 없습니다.