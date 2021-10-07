---
title: IPv6을 통한 익명 인바운드 전자 메일 지원 추가
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 IPv6 원본의 익명 인바운드 전자 메일에 대한 지원을 구성하는 방법을 Exchange Online Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ba52efb6ad18bc0515084b3aee4a8bbdd6c7312
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203870"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>IPv6을 통해 익명 인바운드 전자 메일에 대한 지원을 Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 및 EOP(독립 실행형 Exchange Online Protection) 조직이 Exchange Online IPv6을 통해 익명 인바운드 전자 메일을 지원하는 조직입니다. 원본 IPv6 전자 메일 서버는 다음 요구 사항을 모두 충족해야 합니다.

- 원본 IPv6 주소에는 대상이 IPv6 주소에서 도메인 이름을 찾을 수 있는 유효한 PTR(역방향 DNS 검색) 레코드가 있어야 합니다.

- 보낸 사람은 [RFC 7208](https://tools.ietf.org/html/rfc7208)에 정의되어 있는 SPF 확인 또는 [RFC 6376](http://dkim.org/)에 정의되어 있는 [DKIM 확인](https://www.rfc-editor.org/rfc/rfc6376.txt)을 통과해야 합니다.

조직에서 IPv6을 통해 익명 인바운드 전자 메일을 받으기 전에 관리자는 Microsoft 지원에 문의하여 요청해야 합니다. 지원 요청을 여는 방법에 대한 자세한 내용은 비즈니스 제품에 대한 고객 지원 [문의 - 관리자 도움말을 참조하세요.](../../business-video/get-help-support.md)

조직에서 익명 인바운드 IPv6 메시지 지원이 사용하도록 설정되면 해당 메시지는 서비스에서 제공하는 일반 메시지 필터링을 거치게 됩니다.

## <a name="troubleshooting"></a>문제 해결

- 원본 전자 메일 서버에 IPv6 역방향 DNS 코드 레코드가 없는 경우 다음 오류와 함께 메시지가 거부됩니다.

  > 450 4.7.25 서비스를 사용할 수 없거나 IPv6 주소 보내기[2a01:111:f200:2004::240]에 역방향 DNS 레코드가 있어야 합니다.

- 보낸 사람이 SPF 또는 DKIM 유효성 검사를 통과하지 못하면 다음 오류와 함께 메시지가 거부됩니다.

  > 450 4.7.26 서비스를 사용할 수 없음, IPv6을 통해 전송된 메시지[2a01:111:f200:2004::240]은 SPF 또는 DKIM 유효성 검사를 통과해야 합니다.

- 옵트인하기 전에 익명 IPv6 메시지를 받으려고 하면 다음 오류와 함께 메시지가 거부됩니다.

  > 550 5.2.1 서비스를 사용할 수 없음, [contoso.com]는 IPv6을 통해 전자 메일을 수락하지 않습니다.

## <a name="related-topics"></a>관련 항목

[DKIM으로 서명된 메시지의 유효성 검사 지원](support-for-validation-of-dkim-signed-messages.md)
