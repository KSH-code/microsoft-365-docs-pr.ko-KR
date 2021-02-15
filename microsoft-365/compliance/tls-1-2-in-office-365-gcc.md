---
title: Office 365 GCC High 및 DoD에서 TLS 1.0 및 1.1을 비우기
description: Microsoft 365의 GCC High 및 DoD 환경에서 Microsoft가 TLS 1.1 및 1.0에 대한 지원을 사용 하지 못하게 하는 방법에 대해 논의합니다.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: a0b1fecc9991cd7ba4ac915d3d684d43714014af
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233754"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Office 365 GCC High 및 DoD에서 TLS 1.0 및 1.1을 비우기

## <a name="summary"></a>요약

FedRAMP(Federal Risk and Authorization Management Program)에 대한 최신 준수 표준을 준수하기 위해 Microsoft 365 for GCC High 및 DoD 환경에서 TLS(전송 계층 보안) 버전 1.1 및 1.0을 사용할 수 없습니다. 이 변경 사항은 이전에 Office [365에서 TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용을 준비할 때 Microsoft 지원을 통해 발표했습니다.

데이터의 보안은 매우 중요하며, 서비스 사용에 영향을 줄 수 있는 변경 내용에 대한 투명성을 보장하기 위해 최선을 다하고 있습니다.

Microsoft [TLS 1.0](https://support.microsoft.com/help/3117336) 구현에는 알려진 보안 취약성은 없습니다. 하지만 FedRAMP 규정 준수 표준을 계속 준수하기 위해 최선을 다하고 있습니다. 따라서 2020년 1월 15일 GCC High 및 DoD 환경에서 Office 365에서 TLS 1.1 및 1.0을 사용하지 않도록 설정했습니다. TLS 1.1 및 1.0 종속성 제거 방법에 대한 자세한 내용은 다음 백서를 참조하십시오.

[TLS 1.0 문제 해결](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>추가 정보

2020년 1월 15일부터 GCC High 및 DoD 환경의 Office 365는 TLS 1.1 및 1.0을 더 이상 사용되지 않습니다.

2020년 1월 15일까지 모든 클라이언트 서버 및 브라우저 서버 조합에서 TLS 버전 1.2(또는 이후 버전)를 사용하여 Office 365 서비스에 대한 문제 없이 모든 연결을 만들 수 있도록 해야 합니다. 이 경우 클라이언트 서버와 브라우저 서버의 특정 조합에 대한 업데이트가 필요할 수 있습니다.

2020년 1월 15일까지 TLS 버전 1.2 이상으로 업데이트하지 않는 경우 Office 365에 연결하려고 할 때 문제가 있습니다. 또한 해결의 일부로 TLS 1.2 이상 버전으로 업데이트해야 합니다.

Office 365 GCC High 및 DoD에 대한 무단 액세스를 유지 관리하려면 클라이언트 컴퓨터를 업데이트해야 합니다.

TLS 1.2를 사용하려면 TLS 1.0 또는 TLS 1.1을 통해 Microsoft 365 API를 호출하는 응용 프로그램을 업데이트해야 합니다. .NET 4.5는 기본적으로 TLS 1.1로 설정됩니다. .NET 구성을 업데이트하려면 클라이언트에서 [TLS(전송 계층 보안) 1.2를](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)사용하도록 설정하는 방법을 참조합니다. 자세한 내용은 [Office 365에서 TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 참조하세요.

다음 클라이언트 응용 프로그램에서 TLS 1.2를 사용할 수 없습니다.

- Android 4.3 이하 버전
- Firefox 5.0 이하 버전
- Internet Explorer 8-10(Windows 7 및 이전 버전)
- Internet Explorer 10 on Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 및 이전 버전

Microsoft Online 서비스에 대한 현재 연결을 분석하면 대부분의 서비스 및 끝점에 TLS 1.1 및 1.0 사용이 거의 없는 것으로 표시되기는 하지만 TLS 1.1 및 1.0에 대한 지원이 종료되기 전에 필요한 경우 영향을 받는 클라이언트 또는 서버를 업데이트할 수 있도록 이러한 변경에 대한 공지를 제공합니다. 하이브리드 시나리오 또는 AD FS(Active Directory Federation Services)에 대해 모든 프레미스 인프라를 사용하는 경우 인프라가 TLS 1.2 이상 버전을 사용하는 인바운드 및 아웃바운드 연결을 모두 지원할 수 있는지 확인합니다.

TLS 1.2를 사용할 수 없는 나열된 클라이언트를 사용하는 경우의 정전 외에도 TLS 1.1 및 1.0을 제거하면 다음 Microsoft 제품을 사용할 수 없습니다.

- Lync 전화

## <a name="references"></a>참조

다음 지원 문서에서는 클라이언트가 TLS 1.2를 사용하고 있는지를 확인 하는 데 도움이 되는 지침 및 참조에 대해 설명 합니다.

[Office 365에서 TLS 1.2의 필수 사용 준비](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
