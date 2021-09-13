---
title: High 및 DoD에서 TLS 1.0 Microsoft 365 GCC 1.1을 사용 하지 않습니다.
description: Microsoft가 Microsoft의 고급 및 DoD 환경에서 TLS 1.1 및 1.0에 대한 지원을 GCC 방법을 Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216305"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>High 및 DoD에서 TLS 1.0 Microsoft 365 GCC 1.1을 사용 하지 않습니다.

## <a name="summary"></a>요약

FedRAMP(Federal Risk and Authorization Management Program)에 대한 최신 규정 준수 표준을 준수하기 위해 Microsoft 365 High 및 DoD 환경에서 TLS(전송 계층 보안) 버전 1.1 및 1.0을 GCC 있습니다. 이 변경 사항은 이전에 Microsoft 지원 서비스에서 [TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비에서 Office 365.

데이터의 보안이 중요하며, 서비스 사용에 영향을 줄 수 있는 변경 내용에 대한 투명성을 확보하기 위해 최선을 다하고 있습니다.

Microsoft [TLS 1.0](https://support.microsoft.com/help/3117336) 구현에는 알려진 보안 취약성은 없습니다. 하지만 FedRAMP 규정 준수 표준을 준수하기 위해 계속 최선을 다하고 있습니다. 따라서 2020년 1월 15일, GCC 및 DoD 환경에서는 TLS 1.1 및 Microsoft 365 1.0을 사용하지 않도록 설정했습니다. TLS 1.1 및 1.0 종속성 제거 방법에 대한 자세한 내용은 다음 백서를 참조하십시오.

[TLS 1.0 문제 해결](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>추가 정보

2020년 1월 15일부터 Microsoft 365 High 및 DoD 환경에서 GCC TLS 1.1 및 1.0을 사용하지 않도록 설정됩니다.

2020년 1월 15일까지 모든 클라이언트 서버와 브라우저 서버 조합에서 TLS 버전 1.2(또는 이후 버전)를 사용하여 모든 연결을 설정하는 데 문제가 없는지 Microsoft 365. 이 경우 클라이언트 서버와 브라우저 서버의 특정 조합에 대한 업데이트가 필요할 수 있습니다.

이 SharePoint OneDrive TLS 1.2를 지원하도록 .NET을 업데이트하고 구성해야 합니다. 자세한 내용은 [클라이언트에서 TLS 1.2를 사용하도록 설정하는 방법을 참조하세요.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

High 및 DoD에 대한 무단 액세스를 유지 관리하려면 클라이언트 컴퓨터를 Office 365 GCC 합니다.

TLS 1.2를 사용하려면 TLS Microsoft 365 또는 TLS 1.1을 통해 Microsoft 365 응용 프로그램을 업데이트해야 합니다. .NET 4.5는 기본적으로 TLS 1.1로 설정됩니다. .NET 구성을 업데이트하려면 [클라이언트에서 TLS(전송 계층 보안) 1.2를](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)사용하도록 설정하는 방법을 참조합니다. 자세한 내용은 에서 [TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 Office 365.

다음 클라이언트 응용 프로그램에서 TLS 1.2를 사용할 수 없습니다.

- Android 4.3 이하 버전
- Firefox 5.0 이하 버전
- Internet Explorer 8 7 및 Windows 버전에 대한 Windows–10
- Internet Explorer 10 Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 이전 버전

Microsoft Online 서비스에 대한 현재 연결을 분석한 결과 대부분의 서비스 및 끝점에 TLS 1.1 및 1.0 사용량이 거의 없는 것으로 나타났지만 TLS 1.1 및 1.0에 대한 지원이 종료되기 전에 필요한 경우 영향을 받는 클라이언트 또는 서버를 업데이트할 수 있도록 이 변경에 대한 공지를 제공합니다. 하이브리드 시나리오 또는 AD FS(Active Directory Federation Services)에 대해 모든 사내 인프라를 사용하는 경우 인프라가 TLS 1.2(또는 이후 버전)를 사용하는 인바운드 및 아웃바운드 연결을 모두 지원할 수 있는지 확인합니다.

TLS 1.2를 사용할 수 없는 나열된 클라이언트를 사용하는 경우의 정전 외에도 TLS 1.1 및 1.0을 제거하면 다음 Microsoft 제품을 사용할 수 없습니다.

- Lync 전화

## <a name="references"></a>참조

클라이언트가 TLS 1.2를 사용하고 있는지를 확인 하는 데 도움이 되는 지침 및 참조는 에서 [TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 Office 365.