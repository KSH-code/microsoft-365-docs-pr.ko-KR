---
title: IPv6을 통한 익명 인바운드 전자 메일 지원 추가
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 Exchange Online 및 Exchange Online Protection에서 IPv6 원본의 익명 인바운드 전자 메일에 대 한 지원을 구성 하는 방법을 알 수 있습니다.
ms.openlocfilehash: f2e14fe2e8e46d6085fc3764d3a41382f15049e9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950297"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Microsoft 365에서 i p v 6을 통한 익명 인바운드 전자 메일 지원 추가

Exchange online 사서함 및 독립 실행형 EOP (Exchange Online Protection)가 포함 된 Microsoft 365 조직에서 온-IPv6을 통한 익명 인바운드 전자 메일을 지원 합니다. 원본 IPv6 전자 메일 서버는 다음 요구 사항을 모두 충족 해야 합니다.

- 원본 IPv6 주소에는 대상에서 IPv6 주소 로부터 도메인 이름을 찾을 수 있도록 하는 유효한 PTR (역방향 DNS 조회) 레코드가 있어야 합니다.

- 보낸 사람은 [RFC 7208](https://tools.ietf.org/html/rfc7208)에 정의되어 있는 SPF 확인 또는 [RFC 6376](http://dkim.org/)에 정의되어 있는 [DKIM 확인](https://www.rfc-editor.org/rfc/rfc6376.txt)을 통과해야 합니다.

조직이 i p v 6을 통해 익명 인바운드 전자 메일을 수신 하기 전에 관리자가 Microsoft 지원에 문의 하 여 도움을 요청 해야 합니다. 지원 요청을 여는 방법에 대 한 자세한 내용은 [비즈니스 제품에 대 한 지원 문의-관리자 도움말](../../admin/contact-support-for-business-products.md)을 참조 하세요.

조직에서 익명 인바운드 IPv6 메시지 지원을 사용 하도록 설정한 후에는 메시지가 서비스에서 제공 하는 일반 메시지 필터링을 거칩니다.

## <a name="troubleshooting"></a>문제 해결

- 원본 전자 메일 서버에 IPv6 역방향 DNS 조회 레코드가 없으면 다음 오류가 발생 하 여 메시지가 거부 됩니다.

  > 450 4.7.25 서비스를 사용할 수 없음, 전송 IPv6 주소 [2a01:111: f200:2004:: 240]에 역방향 DNS 레코드가 있어야 합니다.

- 보낸 사람이 SPF 또는 DKIM 유효성 검사를 통과 하지 못하면 다음 오류가 발생 하 여 메시지가 거부 됩니다.

  > 450 4.7.26 서비스를 사용할 수 없음, IPv6을 통해 전송 되는 메시지는 SPF 또는 DKIM 유효성 검사를 통과 해야 합니다.

- 옵트인 하기 전에 익명 IPv6 메시지를 수신 하려고 하면 다음 오류와 함께 메시지가 거부 됩니다.

  > 550 5.2.1 서비스를 사용할 수 없음 [contoso.com]에서는 IPv6을 통한 전자 메일을 수락 하지 않습니다.

## <a name="related-topics"></a>관련 항목

[DKIM으로 서명된 메시지의 유효성 검사 지원](support-for-validation-of-dkim-signed-messages.md)