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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 기본 모바일 및 보안을 설정하여 원격으로 장치 지우기 등의 작업을 수행하여 사용자의 모바일 장치를 보호하고 관리합니다.
ms.openlocfilehash: bbf7cf84dd996a0e548a76978e8fbba58f40c070
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165967"
---
# <a name="set-up-basic-mobility-and-security"></a>기본 이동성 및 보안 설정

기본 제공 기본 모바일 및 보안 for Microsoft 365 iPhone, iPad, Androids 및 Windows 휴대폰과 같은 사용자의 모바일 장치를 보호하고 관리할 수 있습니다. 디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.

질문이 있나요? 일반적인 질문을 해결하기 위한 FAQ는 [Basic Mobility and Security FAQ(질문과](frequently-asked-questions.yml)대답)를 참조하세요. 위임된 관리자 계정을 사용하여 Basic Mobility and Security를 관리할 수는 없습니다. 자세한 내용은 [파트너: 위임된 관리 제공을 참조하세요.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

장치 관리는 보안 & 준수 센터의 일부이기 때문에 기본 이동성 및 보안 설정을 시작해야 합니다.

## <a name="activate-the-basic-mobility-and-security-service"></a>기본 Mobility and Security 서비스 활성화

1. 전역 관리자 Microsoft 365 로그인합니다.

2. 기본 [이동성 및 보안 활성화로 이동 합니다.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   기본 이동성 및 보안을 활성화하는 데 시간이 걸릴 수 있습니다. 완료되면 다음 단계를 설명하는 전자 메일을 받게 됩니다.

## <a name="set-up-mobile-device-management"></a>모바일 장치 관리 설정

서비스가 준비되면 다음 단계를 완료하여 설치를 완료합니다.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>1단계: (필수) 기본 이동성 및 보안에 대한 도메인 구성

사용자 지정 도메인이 Microsoft 365 없는 경우 또는 Windows 장치를 관리하지 않는 경우 이 섹션을 건너뛸 수 있습니다. 그렇지 않으면 DNS 호스트에서 도메인에 대한 DNS 레코드를 추가해야 합니다. 레코드를 이미 추가한 경우 레코드를 사용하여 도메인을 설정하는 Microsoft 365 모두 설정됩니다. 레코드를 추가하고 나면 Microsoft 365 도메인을 사용하는 전자 메일 주소로 Windows 장치에 로그인하는 조직의 사용자가 기본 이동성 및 보안에 등록됩니다.

레코드 설정에 도움이 필요하세요? 도메인 등록 기관을 찾고 등록 기관 이름을 선택하여 도메인에 연결하기 위해 DNS 레코드 추가에 제공된 목록에서 DNS 레코드를 만들기 위한 단계별 [도움말로 이동하세요.](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 이러한 지침을 사용하여 에 설명된 CNAME 레코드를 만들 수 있습니다. Windows 등록을 [Azure AD Premium.](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

두 개의 CNAME 레코드를 추가한 후 보안 & 준수 센터로 돌아가 데이터 손실 방지 장치 관리로 이동하여 다음 단계를  >     완료합니다.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>2단계: (필수) iOS 장치에 대한 APNS 인증서 구성

iPad iPhone과 같은 iOS 장치를 관리하려면 APNs 인증서를 만들어야 합니다.

1. 전역 관리자 Microsoft 365 로그인합니다.

2. 브라우저 유형:  [https://protection.office.com](https://protection.office.com/) .

3. 데이터  **손실 방지 장치** 관리   >  **를 선택하고** iOS 장치에 대한 **APNs 인증서를 선택합니다.**

4. Apple 푸시 알림 인증서 설정 페이지에서 다음 을 **선택합니다.**

5.  **CSR 파일 다운로드를** 선택하고 인증서 서명 요청을 기억할 컴퓨터의 어느   곳에나 저장합니다. 다음 **을 선택합니다.**

6. APNs 인증서 만들기 페이지에서 다음을 클릭합니다.

   - Apple APNS 포털을 선택하여 Apple Push 인증서 포털을 열 수 있습니다.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - 인증서 만들기를 선택하고 사용 약관에 동의합니다.
   - 사용자 컴퓨터로 다운로드한 인증서 서명 요청으로 Microsoft 365 Upload를 선택합니다.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. 다시 Microsoft 365 다음 을 **선택합니다.**

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. 마친  **을 선택합니다.**

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>3단계: (권장) 다단계 인증 설정

MFA는 두 번째 형태의 인증을 Microsoft 365 모바일 장치 등록을 위해 로그인 보안을 유지하도록 합니다. 사용자는 직장 계정 암호를 올바르게 입력한 후 모바일 장치에서 전화 통화, 문자 메시지 또는 앱 알림을 확인해야 합니다. 두 번째 인증 형식이 완료된 후에만 장치를 등록할 수 있습니다. 사용자 장치가 기본 모바일 및 보안에 등록된 후 사용자는 자신의 Microsoft 365 사용하여 리소스에 액세스할 수 있습니다.

Azure AD 포털에서 MFA를 켜는 방법에 대한 자세한 내용은 다단계 인증 설정 [을 참조하세요.](../security-and-compliance/set-up-multi-factor-authentication.md)

MFA를 설정한 후 보안 & 준수 센터로 돌아가 **** 데이터 손실 방지 장치 관리 장치 정책으로 이동하여 다음 단계를   >     >  ****   완료합니다.

### <a name="step-4-recommended-manage-device-security-policies"></a>4단계: (권장) 장치 보안 정책 관리

다음 단계는 장치 보안 정책을 만들고 배포하여 조직 데이터를 보호하는 Microsoft 365 것입니다. 예를 들어 5분 동안 비활성으로 장치를 잠그고 3회 로그인 실패 후 장치를 지우는 정책을 만들어 사용자가 장치를 분실할 경우 데이터 손실을 방지할 수 있습니다.

1. 전역 관리자 Microsoft 365 로그인합니다.

2. 모바일 [장치 관리 활성화를 선택합니다.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) 서비스가 활성화된 경우 대신 정품 인증 단계에 장치 관리에 대한 [링크가 표시됩니다.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. 장치 **정책으로 이동하세요.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 보안 및 모바일 정책 설정":::

4. Create device security policies in Basic Mobility and Security의 단계에 따라 조직에 적합한 장치 보안 정책을 만들고 [배포합니다.](create-device-security-policies.md)

> [!TIP]
>
> - 새 정책을 만들 때 사용자 장치가 정책을 준수하지 않는 경우 액세스 및 보고 정책 위반을 허용하도록 정책을 설정할 수 있습니다. 이렇게 하면 모바일 장치에 대한 액세스를 차단하지 않고 정책의 영향을 미치는 모바일 장치 수를 Microsoft 365.
>
> - 조직의 모든 사용자에게 새 정책을 배포하기 전에 소수의 사용자가 사용하는 디바이스에서 새 정책을 테스트하는 것이 좋습니다.
>
> - 또한 정책을 배포하기 전에 조직에 기본 모바일 및 보안에서 장치 등록이 미칠 수 있는 영향을 알 수 있습니다. 정책을 설정하는 방법에 따라 정책을 준수하지 않는 장치(비호위 장치)가 정책 설정에 액세스하지 못하도록 차단할 수 Microsoft 365. 호환되지 않는 장치에는 장치가 지워진 경우 등록된 디바이스에서 삭제할 수 있는 앱, 사진 및 기타 개인 정보도 있을 수 있습니다. 자세한 내용은 기본 모바일 및 보안에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)

## <a name="make-sure-users-enroll-their-devices"></a>사용자가 장치를 등록하는지 확인

모바일 장치 관리 정책을 만들어 배포한 후 장치 정책을 Microsoft 365 조직에서 사용이 허가된 각 사용자는 다음에 모바일 장치에서 Microsoft 365 로그인할 때 등록 메시지를 받게 됩니다. 등록 및 정품 인증 단계를 완료해야 전자 메일 및 Microsoft 365 액세스할 수 있습니다. 자세한 내용은 기본 모바일 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> 사용자의 기본 설정 언어가 등록 프로세스에서 지원되지 않는 경우 사용자가 등록 알림 및 모바일 장치에서 다른 언어로 단계를 받을 수 있습니다. 모바일 장치에서 지원되는 Microsoft 365 현재 모바일 장치의 등록 프로세스에 지원되지 않습니다.

Android 또는 iOS 장치를 사용 하는 사용자는 등록 프로세스의 일부로 회사 포털 앱을 설치해야 합니다.

## <a name="related-content"></a>관련 콘텐츠

[기본 이동성 및 보안](capabilities.md) 기능(문서)\
[기본 모바일 및 보안에서](create-device-security-policies.md) 장치 보안 정책 만들기(문서)