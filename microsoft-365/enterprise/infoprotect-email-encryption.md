---
title: '6단계: 전자 메일 암호화 구성'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Office 365에 대한 권한이 부여된 액세스 관리를 이해하고 구성합니다.
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067196"
---
# <a name="step-6-configure-email-encryption"></a>6단계: 전자 메일 암호화 구성

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Microsoft 365에는 세 가지 유형의 전자 메일 암호화가 있습니다.

|||
|:-------|:-----|
| OME(Office 메시지 암호화) | 조직 외부에서 전송 되는 Exchange Online 전자 메일에 대 한 암호화 |
| IRM(정보 권한 관리) | 전자 메일과 함께 이동 하는 암호화 및 사용 권한 |
| S/MIME(Secure/Multipurpose Internet Mail Extensions) | 암호화 및 디지털 서명을 사용한 전자 메일 보호 |
|||

## <a name="office-365-message-encryption"></a>Office 365 메시지 암호화

OME를 사용 하는 조직에서는 조직 내부 및 외부의 사용자 간에 암호화 된 전자 메일 메시지를 보내고 받을 수 있습니다. OME는 Outlook.com, Yahoo!, Gmail 및 기타 전자 메일 서비스와 함께 작동 합니다. 전자 메일 메시지 암호화를 사용 하면 의도 된 받는 사람만 메시지를 볼 수 있습니다.

![OME 전자 메일 메시지 암호화](../media/infoprotect-email-encryption/ome-encryption.png)

암호화 조건을 정의 하는 전송 규칙을 설정 합니다. 사용자가 규칙에 맞는 메시지를 보내면 암호화가 자동으로 적용됩니다.

암호화 된 메시지를 보려면 받는 사람은 일회용 암호를 가져오거나 Microsoft 계정으로 로그인 하거나 Microsoft 365와 연결 된 회사 또는 학교 계정으로 로그인 할 수 있습니다. 받는 사람은 암호화된 회신을 보낼 수도 있습니다. 암호화 된 메시지를 보거나 암호화 된 회신을 보내기 위해 자체 Microsoft 365 구독이 필요 하지는 않습니다.

[암호화된 메시지 보기 및 회신](https://docs.microsoft.com/Office365/SecurityCompliance/ome) HTML 파일을 첨부한 암호화된 전자 메일은 암호화된 첨부 전자 메일 메시지를 열고 볼 수 있는 지침과 함께 받는 사람의 사서함에 도착합니다.

## <a name="irm"></a>IRM

Microsoft 365의 IRM을 사용 하면 정보를 추가 암호화와 함께 보호 하 고 사용자가 액세스할 수 있는 사람을 지정 하는 지능형 정책을 적용 하는 데 도움이 됩니다. 전자 메일 메시지의 경우 암호화에 IRM을 사용 하 고 사용 제한을 적용할 수 있습니다. 예를 들어 일부 받는 사람에 게 전자 메일을 관리 하는 모든 기능이 있고 전자 메일을 인쇄 하거나 전달할 수 없도록 지정할 수 있습니다. 

IRM 정책은 Microsoft 365 내에서 구성 되며 SharePoint Online 및 전자 메일 메시지의 문서에 적용할 수 있습니다. IRM으로 보호 된 전자 메일에 적용 되 고 적용 된 정책 설정이 포함 됩니다. 

![전자 메일 메시지의 IRM 보호](../media/infoprotect-email-encryption/irm-protection.png)

받는 사람이 포함 된 정책을 사용 하 여 전자 메일을 여는 경우 정책 설정을 사용 하 여 메시지의 암호를 해독 하 고 받는 사람이이 작업을 수행할 수 있는 작업을 결정 합니다. 

전송 보호 규칙과 달리, Outlook 보호 규칙은 사용자가 덜 중요한 콘텐츠에 대해서는 보호 기능을 끌 수 있도록 구성할 수 있습니다.

## <a name="smime"></a>S/MIME

S/MIME은 메시지를 암호화 하 고 디지털 서명할 수 있도록 하는 디지털 인증서 기반 전자 메일 기반 보호 솔루션입니다. 메시지 암호화를 사용하면 받는 사람만 메시지를 열고 읽도록 할 수 있습니다. 디지털 서명을 사용 하면 받는 사람이 보낸 사람의 id를 확인 하 여 보낸 사람만 보낸 사람을 확인할 수 있습니다.

![전자 메일 메시지의 S/MIME 보호](../media/infoprotect-email-encryption/smime-protection.png)

S/MIME을 사용 하 여 Microsoft 365 구독 또는 외부 사용자의 다른 사서함에 전자 메일을 보낼 수 있습니다.
메시지를 암호화 하거나 암호를 해독 하 고 디지털 서명을 만들고 확인 하기 위한 공개 키와 개인 키는 포함 된 디지털 인증서를 사용 하 여 메시지 암호화 및 디지털 서명을 둘 다 사용할 수 있습니다.
S/MIME을 사용 하려면 각 받는 사람에 대 한 공개 키가 있어야 합니다. 받는 사람은 안전한 상태로 유지 해야 하는 개인 키를 유지 관리 합니다. 개인 키가 손상 된 경우 새 디지털 인증서를 얻고 모든 잠재적 보낸 사람에 게 공개 키를 재배포 해야 합니다.

자세한 내용은 [메시지 서명 및 암호화에 대 한 S/MIME](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)를 참조 하세요.


중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step6)을 확인하세요.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![7단계](../media/stepnumbers/Step7.png)|[Office 365에 대한 권한이 부여된 액세스 관리 구성](infoprotect-configure-privileged-access-management.md)|
