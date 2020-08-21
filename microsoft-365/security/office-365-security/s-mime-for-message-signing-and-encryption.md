---
title: Exchange Online에서 암호화를 위한 S/MIME - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 관리자는 Exchange Online에서 S/MIME(Secure/Multipurpose Internet Mail Extensions)을 사용하여 메일을 암호화하고 디지털 서명하는 방법을 배를 찾을 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca865fa8ef658b4715d18e09fe9cbc1cffb201e6
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845923"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>Exchange Online의 메시지 서명 및 암호화를 위한 S/MIME

S/MIME(Secure/Multipurpose Internet Mail Extensions)은 디지털 서명 및 암호화된 메시지를 보내기 위해 널리 받아치는 방법(이나 프로토콜)입니다. S/MIME을 사용하여 전자 메일을 암호화하고 디지털 서명할 수 있습니다. S/MIME을 전자 메일 메시지와 함께 사용하는 경우 이 메시지를 받는 사람이 받은 편지함에 보낸 사람이 시작된 정확한 메시지라는 사실을 알수 있도록 도와주세요. 또한 메시지를 받는 사람이 특정한 보낸 사람이 보낸 사람이 보낸 사명이 고지한다고 할 도로정책을 보입니다. 이를 위해 S/MIME는 인증, 메시지 무결성 및 출신 취소(디지털 서명 사용) 등의 암호화 보안 서비스를 제공합니다. 전자 메시지에 대한 개인 정보 및 데이터 보안(암호화 사용)을 향상시키는 데에도 도움이 됩니다. 전자 메일의 컨텍스트에서 S/MIME 기록 및 아키텍처에 대한 전체 배경정보를 보려면 [S/MIME 이해를 참조하세요.](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))

Exchange Online 관리자는 조직의 사서함에 대해 S/MIME 기반 보안을 사용하도록 설정할 수 있습니다. 아래에 링크되어 있는 항목의 지침에 따라 Exchange Online PowerShell을 사용하여 S/MIME을 설정합니다. 지원되는 전자 메일 클라이언트에서 S/MIME을 사용하려면 조직의 사용자에게 서명 및 암호화용으로 발급된 인증서가 있어야 하며 데이터를 온-프레미스 AD DS(Active Directory 도메인 서비스)에 게시해야 합니다. AD DS는 인터넷의 클라우드 서비스 또는 원격 시설이 아닌 관리자가 제어할 수 있는 물리적 위치의 컴퓨터에 있어야 합니다. AD DS에 대한 자세한 내용은 [Active Directory 도메인 서비스 개요를 참조하십시오.](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)

## <a name="supported-scenarios-and-technical-considerations"></a>지원되는 시나리오 및 기술 고려 사항

다음 끝점에서 작동하도록 S/MIME을 설정할 수 있습니다.

- Outlook 2010 이상
- 웹용 Outlook(이전 Outlook Web App)
- EAS(Exchange ActiveSync)

이러한 각 엔드점에 대해 S/MIME을 설정하기 위해 수행되는 단계는 약간씩 다릅니다. 일반적으로 다음 단계를 수행해야 합니다.

1. S/MIME 인증서를 발급하도록 Windows 기반 CA(인증 기관)를 설치하고 공개 키 인프라를 설정합니다. 타사 인증서 공급자가 발급한 인증서도 지원됩니다. 자세한 내용은 [Active Directory 인증서 서비스 개요](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))를 참조하세요.

   **참고:**

   - 타사 CA에서 발급된 인증서는 모든 클라이언트와 장치에서 자동으로 신뢰하는 이점이 있습니다. 내부에서 발급된 인증서는 클라이언트와 디바이스에서 자동으로 신뢰되지 않기는 하며, 일부 장치(예: 전화)는 개인 인증서를 신뢰하도록 구성할 수 없습니다.

   - 사용자에게 인증서를 발급하는 루트 인증서 대신 중간 인증서를 사용하여 사용자에게 인증서를 발급하는 것이 좋습니다. 이렇게 하면 인증서를 해지하고 다시 발급해야 하는 경우 루트 인증서가 그에도 의도하지 않습니다.

2. **UserSMIMECertificate** 및/또는 UserCertificate 특성의 온-프레미스 AD DS 계정으로 사용자 **인증서를** 게시합니다.

3. Exchange Online 조직의 경우 해당하는 Azure AD Connect 버전을 사용하여 AD DS에서 Azure Active Directory로 사용자 인증서를 동기화합니다. 그러면 이러한 인증서가 Azure Active Directory에서 Exchange Online 디렉터리로 동기화되며 받는 사람에 대한 메시지를 암호화할 때 사용됩니다.

4. S/MIME의 유효성을 검사하기 위해 가상 인증서 모음을 설정합니다. 이 정보는 전자 메일의 서명 유효성을 검사하여 전자 메일이 신뢰할 수 있는 인증서를 사용하여 서명되었음을 확인하는 데 웹용 Outlook에서 사용됩니다.

5. S/MIME을 사용하도록 Outlook 또는 EAS 끝점을 설정합니다.

> [!NOTE]
> Mac, iOS, Android 또는 기타 비 Windows 디바이스에서 Outlook에 S/MIME 컨트롤을 설치할 수 없습니다. 자세한 내용은 웹에서 [Outlook에 S/MIME을 사용하여 메시지 암호화를 참조하십시오.](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)

## <a name="setup-smime-with-outlook-on-the-web"></a>웹용 Outlook에서 S/MIME 설정

웹용 Outlook에서 Exchange Online에 대해 S/MIME을 설정하려면 다음 주요 단계를 수행합니다.

1. [웹용 Outlook용 S/MIME 설정 구성](configure-s-mime-settings-for-outlook-web-app.md)
2. [S/MIME 유효성 검사를 위한 가상 인증서 컬렉션 설정](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [S/MIME용으로 Office 365에 사용자 인증서 동기화](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>관련 메시지 암호화 기술

메시지 보안의 중요도가 점점 중요해지면서 관리자는 메시지 보호 원칙 및 개념을 이해해야 합니다. 특히 S/MIME(S/MIME 포함)의 다양한 보호 관련 기술(S/MIME 포함)도 점점 증가하여 이러한 이해의 중요성도 중요합니다. S/MIME 및 전자 메일과 관련하여 S/MIME이 작동하는 방식에 대해 자세히 알아보려면 [S/MIME 이해](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))를 참조하세요. 다양한 암호화 기술이 연동되어 저장된 메시지 및 전송 중인 메시지를 보호합니다. S/MIME은 다음 기술과 동시에 사용할 수 있지만 이러한 기술에 종속되는 것은 아닙니다.

- **TLS(전송 계층 보안)** 는 스누핑 및 도청을 방지하기 위해 전자 메일 서버 간의 터널/경로를 암호화합니다.

- **Secure Sockets Layer(SSL)는** 전자 메일 클라이언트와 Microsoft 365 서버 간의 연결을 암호화합니다.

- **BitLocker**는 데이터 센터의 하드 드라이브에 저장된 데이터를 암호화하여 무단으로 액세스하는 사용자가 해당 데이터를 읽을 수 없도록 합니다.

### <a name="smime-compared-with-office-365-message-encryption"></a>Office 365 메시지 암호화와 S/MIME 비교

S/MIME를 사용하려면 업무 간 및 기업 간의 소비자의 경우가 종종 사용되는 인증서 및 게시 인프라가 필요합니다. 사용자는 S/MIME에서 암호화 키를 제어하고 전송한 메시지마다 암호화 키를 사용할지 여부를 선택할 수 있습니다. Outlook과 같은 전자 메일 프로그램은 신뢰할 수 있는 루트 인증 기관 위치를 검색하여 서명의 디지털 서명 및 확인을 수행합니다. Office 365 메시지 암호화는 조직 내부 또는 외부의 모든 사람에게 전송되는 메일을 암호화하기 위해 개별 사용자가 구성할 수 있고 개별 사용자가 구성할 수 있는 정책 기반 암호화 서비스입니다. RMS(Azure 권한 관리)를 기반으로 구축되며 공개 키 인프라를 사용하지 않는 온라인 서비스입니다. Office 365 메시지 암호화는 조직의 브랜드로 메일을 사용자 지정하는 기능과 같은 추가 기능도 제공합니다. Office 365 메시지 암호화에 대한 자세한 내용은 [Office 365의 암호화를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/encryption)

## <a name="more-information"></a>추가 정보

[웹용 Outlook](https://docs.microsoft.com/exchange/exchange-admin-center)

[보안 메일(2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
