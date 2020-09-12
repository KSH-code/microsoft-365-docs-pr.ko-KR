---
title: 기본 이동성 및 보안 설정
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 기본 이동성 및 보안을 설정 하 여 사용자의 모바일 장치를 보호 하 고 관리 합니다.
ms.openlocfilehash: 079593381d6395c18cd80f3eeab2e16837a2d27a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545811"
---
# <a name="set-up-basic-mobility-and-security"></a>기본 이동성 및 보안 설정

기본 제공 되는 Microsoft 365 용 기본 기능을 사용 하면 Iphone, Ipad, Androids 및 Windows phone과 같은 사용자의 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다. 디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.

질문이 있나요? 일반적인 질문을 해결 하는 데 도움이 되는 FAQ를 보려면 [기본 Mobility And Security 자주 묻는 질문 (FAQ)](frequently-asked-questions.md)을 참조 하십시오. 위임 된 관리자 계정을 사용 하 여 기본 이동성 및 보안을 관리할 수는 없습니다. 자세한 내용은 [파트너: 위임 된 관리 제공](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)을 참조 하십시오. 

장치 관리가 보안 & 준수 센터의 일부 이므로 MDM 설치를 시작 하기 위해 이동 해야 합니다.

## <a name="activate-the-basic-mobility-and-security-service"></a>기본 모바일 및 보안 서비스 활성화

1. 전역 관리자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.

2. [기본 이동성 및 보안 활성화](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)로 이동 합니다.

   기본 이동성 및 보안을 활성화 하는 데 약간의 시간이 걸릴 수 있습니다. 완료 되 면 수행할 다음 단계를 설명 하는 전자 메일을 받게 됩니다.

## <a name="set-up-mobile-device-management"></a>모바일 장치 관리 설정

서비스가 준비 되 면 다음 단계를 완료 하 여 설치를 완료 합니다.

### <a name="step-1-required-configure-domains-for-mdm"></a>1 단계: (필수) MDM에 대 한 도메인 구성

Microsoft 365와 연결 된 사용자 지정 도메인이 없거나 Windows 장치를 관리 하 고 있지 않은 경우에는이 섹션을 건너뛸 수 있습니다. 그렇지 않으면 DNS 호스트에서 도메인에 대 한 DNS 레코드를 추가 해야 합니다. Microsoft 365을 사용 하 여 도메인을 설정 하는 과정에서 이미 레코드를 추가한 경우 모두 설정 됩니다. 레코드를 추가한 후에 사용자 지정 도메인을 사용 하는 전자 메일 주소로 Windows 디바이스에 로그인 하는 Microsoft 365 조직의 사용자는 기본 Mobility and Security에서 등록으로 리디렉션됩니다.

레코드를 설정 하는 데 도움이 필요 하세요? 도메인 등록 기관을 찾고, 등록자 이름을 선택 하 여 [도메인 연결을 위한 dns 레코드 추가](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)에 제공 된 목록에서 dns 레코드를 만드는 방법에 대 한 단계별 도움말로 이동 합니다. 이러한 지침을 사용 하 여 [AZURE AD Premium 없이 Windows 등록을 단순화](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)하는 방법에 설명 된 CNAME 레코드를 만들 수 있습니다.

두 CNAME 레코드를 추가한 후에는 보안 & 준수 센터로 돌아간 후 **데이터 손실 방지**  >  **장치 관리**로 이동   하 여 다음 단계를 완료 합니다.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>2 단계: (필수) iOS 장치용 APNs 인증서 구성

IPad 및 Iphone와 같은 iOS 장치를 관리 하려면 APNs 인증서를 만들어야 합니다.

1. 전역 관리자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.

2. 브라우저에서 다음을 입력  [https://protection.office.com](https://protection.office.com/) 합니다.

3.  **데이터 손실 방지**   >  **장치 관리**를 선택 하 고 **iOS 장치용 APNs 인증서**를 선택 합니다.

4. Apple 푸시 알림 인증서 설정 페이지에서 **다음**을 선택 합니다.

5.  **CSR 파일 다운로드**   를 선택 하 고 사용자 컴퓨터의 원하는 위치에 인증서 서명 요청을 저장 합니다.  **다음**을 선택 합니다.

6. APNs 인증서 만들기 페이지에서 다음을 수행 합니다.

   - Apple APNS Portal을 선택 하 여 Apple Push Certificate Portal을 엽니다.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - 인증서 만들기 및 사용 약관에 동의를 선택 합니다.
   - Microsoft 365 및 selectUpload에서 컴퓨터로 다운로드 한 인증서 서명 요청으로 이동 합니다.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365으로 돌아가 **다음**을 선택 합니다.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9.   **마침을**선택 합니다.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>3 단계: (권장) multi-factor authentication 설정

MFA는 두 번째 형태의 인증을 요구 하 여 모바일 장치 등록을 위해 Microsoft 365에 로그인 하는 기능을 보호 하는 데 도움이 됩니다. 사용자는 회사 계정 암호를 올바르게 입력 한 후에 모바일 장치에서 전화 통화, 문자 메시지 또는 앱 알림을 승인 해야 합니다. 이 두 번째 인증 형식이 완료 된 후에만 장치를 등록할 수 있습니다. 사용자 장치를 기본 Mobility and Security에 등록 하면 사용자는 자신의 회사 계정만 사용 하 여 Microsoft 365 리소스에 액세스할 수 있습니다.

Azure AD 포털에서 MFA를 설정 하는 방법에 대 한 자세한 내용은 [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255)를 참조 하세요.

MFA를 설정한 후 보안 & 준수 센터로 돌아간 후 **데이터 손실 방지**   >  **장치 관리**   >  **장치 정책**으로 이동   하 여 다음 단계를 완료 합니다.

### <a name="step-4-recommended-manage-device-security-policies"></a>4 단계: (권장) 장치 보안 정책 관리

다음 단계에서는 Microsoft 365 조직 데이터를 보호 하는 데 도움이 되는 장치 보안 정책을 만들고 배포 합니다. 예를 들어, 사용자가 장치를 분실 한 경우, 5 분 동안 비활성 상태에서 장치를 잠그는 정책을 만들어 장치가 손실 되 면 데이터 손실을 방지할 수 있습니다 (로그인 오류 3 회).

1. 전역 관리자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.

2.  [모바일 장치 관리 활성화](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)를 선택 합니다. 서비스가 활성화 되 면 인증 단계 대신 [장치 관리](https://admin.microsoft.com/adminportal/home#/MifoDevices)링크가 표시 됩니다   .

3.  **장치 정책**으로 이동 합니다.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 보안 및 이동성 정책 설정":::

4.  [기본 이동성 및 보안에서 장치 보안 정책 만들기](create-device-security-policies.md)의 단계에 따라 조직에 적합 한 장치 보안 정책을 만들고 배포 합니다.

> [!TIP]
>
> - 새 정책을 만들 때는 액세스를 허용 하 고 사용자 장치가 정책을 준수 하지 않는 정책 위반을 보고 하는 정책을 설정할 수 있습니다. 이를 통해 Microsoft 365에 대 한 액세스를 차단 하지 않고 정책의 영향을 받는 모바일 장치 수를 확인할 수 있습니다.
>
> - 조직의 모든 사람에 게 새 정책을 배포 하기 전에 소수의 사용자가 사용 하는 장치에서이를 테스트 하는 것이 좋습니다.
>
> - 또한 정책을 배포 하기 전에 조직에서 기본 이동성 및 보안의 장치 등록에 대 한 잠재적인 영향을 알 수 있도록 합니다. 정책을 설정 하는 방법에 따라 정책 (비규격 장치)을 준수 하지 않는 장치는 Microsoft 365에 액세스 하지 못하도록 차단 될 수 있습니다. 비규격 장치에는 장치를 초기화 하는 경우 등록 된 장치에서 삭제할 수 있는 앱, 사진 및 기타 개인 정보가 포함 될 수도 있습니다. 자세한 내용은 [기본 Mobility And Security에서 모바일 장치 초기화](wipe-mobile-device.md)를 참조 하세요.

## <a name="make-sure-users-enroll-their-devices"></a>사용자가 자신의 장치를 등록 하는지 확인

모바일 장치 관리 정책을 만들고 배포한 후에는 다음에 모바일 장치에서 Microsoft 365에 로그인 할 때 장치 정책이 적용 되는 조직의 라이선스 Microsoft 365 사용자가 등록 메시지를 받습니다. Microsoft 365 전자 메일 및 문서에 액세스 하려면 먼저 등록 및 정품 인증 단계를 완료 해야 합니다. 자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device.md)을 참조 하세요.

> [!IMPORTANT]
> 등록 프로세스에서 사용자의 기본 설정 언어를 지원 하지 않는 경우 사용자는 모바일 장치에서 다른 언어로 등록 알림 및 단계를 수신할 수 있습니다. Microsoft 365에서 지원 되는 일부 언어는 현재 모바일 장치에서 등록 프로세스에 대해 지원 되지 않습니다.

Android 또는 iOS 장치를 사용 하는 사용자는 등록 프로세스의 일부로 회사 포털 앱을 설치 해야 합니다.

## <a name="related-topics"></a>관련 항목

[기본 이동성 및 보안 기능](capabilities.md)<br/>
[기본 모바일 및 보안에서 장치 보안 정책 만들기](create-device-security-policies.md)