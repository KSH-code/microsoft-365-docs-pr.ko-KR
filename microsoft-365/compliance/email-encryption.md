---
title: Microsoft 365의 전자 메일 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: OME(Office 365 메시지 암호화), S/MIME, IRM(정보 권한 관리)를 비롯한 Microsoft 365 암호화 옵션을 비교하고 TLS(전송 계층 보안)에 대해 자세히 알아봅니다.
ms.openlocfilehash: a882a0bb9597fdb1eb0bf5dcf520b8ced834af5e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218952"
---
# <a name="email-encryption"></a>전자 메일 암호화

이 문서에서는 OME(Office 365 메시지 암호화), S/MIME, IRM(정보 권한 관리)을 포함한 Microsoft 365의 암호화 옵션을 비교하고 TLS(전송 계층 보안)을 소개합니다.
  
Microsoft 365는 전자 메일 보안에 대한 비즈니스 요구를 충족하는데 도움이 되는 여러 가지 암호화 옵션을 제공합니다. 이 문서에서는 Office 365에서 전자 메일을 암호화하는 세 가지 방법을 제공합니다. Office 365의 모든 보안 기능에 대한 자세한 내용을 보려면 [office 365 보안 센터](https://go.microsoft.com/fwlink/p/?LinkID=282470)를 방문하세요. 이 문서에서는 Office 365에서 Microsoft 365 관리자가 전자 메일 보안을 위해 사용할 수 있는 세 가지 암호화 유형을 소개합니다.
  
- OME(Office 메시지 암호화)

- S/MIME(Secure/Multipurpose Internet Mail Extensions)

- IRM(정보 권한 관리)

## <a name="how-microsoft-365-uses-email-encryption"></a>Microsoft 365에서 전자 메일 암호화를 사용하는 방법

암호화는 승인된 수신자만 정보를 해독하고 사용할 수 있도록 정보를 인코딩하는 프로세스입니다. Microsoft 365는 서비스와 고객 제어라는 두 가지 방식으로 암호화를 사용합니다. 서비스에서 암호화는 기본적으로 Microsoft 365에서 사용됩니다. 아무것도 구성할 필요가 없습니다. 예를 들어 Microsoft 365는 TLS(전송 계층 보안)를 사용하여 두 서버 간의 연결 또는 세션을 암호화합니다. 
  
일반적으로 전자 메일 암호화가 작동하는 방식은 다음과 같습니다.
  
- 보내는 사람의 컴퓨터에서 또는 메시지를 전송하는 동안 중앙 서버를 통해 메시지가 암호화되거나 일반 텍스트에서 읽을 수 없는 암호 텍스트로 변환됩니다.

- 메시지를 누군가 가로채는 경우 읽지 못하도록 보호하기 위해 메시지는 전송되는 동안 암호 텍스트로 남아 있습니다.

- 받는 사람이 메시지를 받으면 다음 두 가지 방법 중 하나를 통해 메시지가 읽을 수 있는 일반 텍스트 형식으로 다시 변환됩니다.

  - 받는 사람의 컴퓨터가 메시지의 암호를 해독하는 키를 사용하거나

  - 중앙 서버가 받는 사람의 ID를 확인한 후 받는 사람을 대신하여 메시지의 암호를 해독합니다.

Microsoft 365 내에서 조직 간의 통신, Microsoft 365와 Microsoft 365 외부의 신뢰할 수 있는 비즈니스 파트너 간의 통신 등 Microsoft 365에서 통신 보안을 확보하는 방법에 대한 자세한 내용은 [Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법](exchange-online-uses-tls-to-secure-email-connections.md)을 참조하세요.
    
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365에서 사용할 수 있는 전자 메일 암호화 옵션 비교

|전자 메일 암호화 기술|![OME를 설명하는 개념 아트워크.](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![IRM을 설명하는 개념 아트워크](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![SMIME를 설명하는 개념 아트워크](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|OME(Office 365 메시지 암호화)란 무엇입니까?|OME(Office 365 메시지 암호화)는 Azure RMS(권한 관리)를 기반으로 구축된 서비스로, 대상의 전자 메일 주소(Gmail, Yahoo! Mail, Outlook.com 등)에 상관없이 사용자 조직 내부 또는 외부 사람에게 암호화된 전자 메일을 보낼 수 있습니다. <br/> 관리자는 암호화 조건을 정의하는 전송 규칙을 설정할 수 있습니다. 사용자가 규칙에 맞는 메시지를 보내면 암호화가 자동으로 적용됩니다. <br/> 암호화된 메시지를 보려면 받는 사람이 일회용 암호를 얻어 Microsoft 계정에 로그인하거나 Office 365와 연결된 회사 또는 학교 계정을 사용하여 로그인할 수 있습니다. 받는 사람은 암호화된 회신을 보낼 수도 있습니다. 암호화된 메시지를 보거나 암호화된 회신을 보내는 데는 Microsoft 365 구독이 필요하지 않습니다.|IRM은 전자 메일 메시지에 사용 제한을 적용하는 암호화 솔루션입니다. 권한이 없는 사용자가 중요한 정보를 인쇄, 전달 또는 복사하는 것을 방지할 수 있습니다. <br/> Microsoft 365의 IRM 기능은 Azure RMS(Azure 권한 관리)를 사용합니다.|S/MIME는 메시지를 암호화하고 메시지에 디지털 서명을 할 수 있는 인증서 기반의 암호화 솔루션입니다. 메시지 암호화를 사용하면 받는 사람만 메시지를 열고 읽도록 할 수 있습니다. 디지털 서명은 받는 사람이 보낸 사람의 ID를 확인할 수 있도록 합니다. <br/> 디지털 서명과 메시지 암호화 둘 모두는 디지털 서명을 확인하고 메시지를 암호화 또는 암호 해독하는 키가 포함된 고유한 디지털 인증서를 사용하여 가능해졌습니다. <br/> S/MIME을 사용하려면 받는 사람마다 파일에 공개 키가 있어야 합니다. 받는 사람은 자신의 개인 키를 유지 관리해야 합니다. 이러한 키는 안전하게 보호되어야 합니다. 받는 사람의 개인 키가 손상된 경우 받는 사람은 새 비공개 키를 찾은 다음 모든 잠재적 보낸 사람에게 공용 키를 재배포해야 합니다.|
|어떤 작업을 수행하나요?|OME: <br/> 내부 또는 외부 받는 사람에게 보내는 메시지를 암호화합니다. <br/>  사용자가 Outlook.com, Yahoo! Mail, Gmail 등의 전자 메일 주소로 암호화된 메시지를 보낼 수 있습니다. <br/>  관리자가 전자 메일 확인 포털을 사용자 지정하여 조직의 브랜드를 반영할 수 있습니다. <br/> Microsoft가 사용자 대신 키를 안전하게 관리합니다. <br/> 브라우저에서 암호화된 메시지(HTML 첨부 파일로 전송)를 열 수 있는 한 특별한 클라이언트 쪽 소프트웨어가 필요하지 않습니다.|IRM: <br/> 암호화 및 사용 제한을 사용하여 전자 메일 메시지 및 첨부 파일을 온라인/오프라인으로 보호합니다. <br/> 관리자가 전송 규칙 또는 Outlook 보호 규칙을 설정할 수 있도록 함으로써 IRM을 자동으로 적용하여 메시지를 선택할 수 있습니다. <br/> Outlook 또는 웹용 Outlook(이전 Outlook Web App)에서 템플릿을 수동으로 적용할 수 있도록 합니다.|S/MIME는 디지털 서명으로 기밀성 보낸사람 인증을 확인하고 암호화로 메시지 기밀을 확인합니다.|
|어떤 작업을 하지 않나요?|OME에서는 메시지에 사용 제한을 적용할 수 없습니다. 예를 들어 받는 사람이 암호화된 메시지를 전달하거나 인쇄하지 못하게 하는 데 이 기능을 사용할 수 없습니다.|일부 응용 프로그램은 일부 장치에서 IRM 전자 메일을 지원하지 않을 수 있습니다. 이러한 제품과 IRM 전자 메일을 지원하는 기타 제품에 대한 자세한 내용은 [클라이언트 디바이스 기능](/azure/information-protection/requirements#BKMK_ClientCapabilities)을 참조하세요.|S/MIME는 암호화된 메시지에 대한 맬웨어, 스팸 또는 정책 검색을 허용하지 않습니다.|
|권장 사항 및 예제 시나리오|소비자인지 다른 기업이든 조직 외부에 있는 사람에 중요한 비즈니스 정보를 보내고 싶은 경우 OME를 사용하는 것이 좋습니다. 예를 들어:  <br/>  은행 직원이 고객에게 신용 카드 청구서를 보내는 경우  <br/>  병원에서 환자에게 의료 기록을 보내는 경우  <br/>  한 변호사가 다른 변호사에게 기밀 법적 정보를 보내는 경우|사용 제한뿐만 아니라 암호화도 적용하려는 경우 IRM을 사용하는 것이 좋습니다. 예를 들면 다음과 같습니다.  <br/>  자신의 팀에 새 제품 관련 기밀 정보를 보내는 관리자가 “전달 금지” 옵션을 적용하는 경우  <br/>  임원이 Office 365를 사용하는 파트너의 첨부 파일이 포함된 입찰 제안서를 다른 회사와 공유해야 하는데 전자 메일과 첨부 파일이 모두 보호되어야 하는 경우|사용자의 조직 또는 받는 사람의 조직이 진정한 피어 투 피어 암호화를 요구하는 경우 S/MIME를 사용하는 것이 좋습니다.  <br/>  S/MIME는 다음과 같은 시나리오에서 가장 많이 사용됩니다.  <br/>  정부 기관이 다른 정부 기관과 통신하는 경우  <br/>  기업이 정부 기관과 통신하는 경우|
||

## <a name="what-encryption-options-are-available-for-my-microsoft-365-subscription"></a>내 Microsoft 365 구독에 대해 사용할 수 있는 암호화 옵션은 무엇이 있나요?

Microsoft 365 구독의 전자 메일 암호화 옵션에 대한 내용은 [Exchange Online 서비스 설명](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)을 참조하세요. 여기서 다음 암호화 기능에 대한 정보를 찾을 수 있습니다.
  
- IRM 기능 및 OME 모두를 비롯한 Azure RMS

- S/MIME

- TLS

- BitLocker를 통한 보관된 데이터 암호화

Microsoft 365와 함께 PGP(Pretty Good Privacy)와 같은 타사 암호화 도구를 사용할 수도 있습니다. Microsoft 365는 PGP/MIME를 지원하지 않으므로 PGP/Inline만을 사용하여 PGP-암호화된 전자 메일을 보내고 받을 수 있습니다.

## <a name="what-about-encryption-for-data-at-rest"></a>보관된 데이터의 암호화는 어떻게 하나요?

“보관된 데이터”는 활성 전송 중이 아닌 데이터를 나타냅니다. Microsoft 365에서는 BitLocker 드라이브 암호화를 사용하여 보관된 전자 메일 데이터를 암호화합니다. BitLocker는 Microsoft 데이터 센터의 하드 드라이브를 암호화하여 무단 액세스에 대한 보호를 강화합니다. 자세한 내용은 [BitLocker 개요](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831713(v=ws.11))를 참조하세요.
  
## <a name="more-information-about-email-encryption-options"></a>전자 메일 암호화 옵션에 대한 자세한 정보

이 문서와 TLS에서의 전자 메일 암호화 옵션에 대한 자세한 내용은 다음 문서를 참조하세요.
  
**OME**
  
[OME(Office 365 메시지 암호화)](ome.md)
  
**IRM**
  
[Exchange Online의 정보 권한 관리](./information-rights-management-in-exchange-online.md)
  
[Azure 권한 관리란?](/azure/information-protection/what-is-azure-rms)
  
**S/MIME**
  
[메시지 서명 및 암호화를 위한 S/MIME](/Exchange/policy-and-compliance/smime/smime)
  
[S/MIME 이해](/previous-versions/tn-archive/aa995740(v=exchg.65))
  
[공개 키 암호화 이해](/previous-versions/tn-archive/aa998077(v=exchg.65))
  
**TLS**
  
[커넥터를 사용하여 사용자 지정 메일 흐름 구성하기](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
