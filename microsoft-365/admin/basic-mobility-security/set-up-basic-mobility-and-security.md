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
ms.openlocfilehash: 0d62c209d4eb9d0da9096ccd5ca2d4a387becf95
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337010"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="d1127-103">기본 이동성 및 보안 설정</span><span class="sxs-lookup"><span data-stu-id="d1127-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="d1127-104">기본 제공 되는 Microsoft 365 용 기본 기능을 사용 하면 Iphone, Ipad, Androids 및 Windows phone과 같은 사용자의 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="d1127-105">디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="d1127-106">질문이 있나요?</span><span class="sxs-lookup"><span data-stu-id="d1127-106">Have questions?</span></span> <span data-ttu-id="d1127-107">일반적인 질문을 해결 하는 데 도움이 되는 FAQ를 보려면 [기본 Mobility And Security 자주 묻는 질문 (FAQ)](basic-mobility-and-security-frequently-asked-questions.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1127-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](basic-mobility-and-security-frequently-asked-questions.md).</span></span> <span data-ttu-id="d1127-108">위임 된 관리자 계정을 사용 하 여 기본 이동성 및 보안을 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="d1127-109">자세한 내용은 [파트너: 위임 된 관리 제공](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1127-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="d1127-110">장치 관리가 보안 & 준수 센터의 일부 이므로 MDM 설치를 시작 하기 위해 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off MDM setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="d1127-111">기본 모바일 및 보안 서비스 활성화</span><span class="sxs-lookup"><span data-stu-id="d1127-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="d1127-112">전역 관리자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-112">Sign in to Microsoft 365 with your global admin account.</span></span>
    

2. <span data-ttu-id="d1127-113">[기본 이동성 및 보안 활성화](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>
    
    <span data-ttu-id="d1127-114">기본 이동성 및 보안을 활성화 하는 데 약간의 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="d1127-115">완료 되 면 수행할 다음 단계를 설명 하는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="d1127-116">모바일 장치 관리 설정</span><span class="sxs-lookup"><span data-stu-id="d1127-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="d1127-117">서비스가 준비 되 면 다음 단계를 완료 하 여 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-mdm"></a><span data-ttu-id="d1127-118">1 단계: (필수) MDM에 대 한 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="d1127-118">Step 1: (Required) Configure domains for MDM</span></span>

<span data-ttu-id="d1127-119">Microsoft 365와 연결 된 사용자 지정 도메인이 없거나 Windows 장치를 관리 하 고 있지 않은 경우에는이 섹션을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="d1127-120">그렇지 않으면 DNS 호스트에서 도메인에 대 한 DNS 레코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="d1127-121">Microsoft 365을 사용 하 여 도메인을 설정 하는 과정에서 이미 레코드를 추가한 경우 모두 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="d1127-122">레코드를 추가한 후에 사용자 지정 도메인을 사용 하는 전자 메일 주소로 Windows 디바이스에 로그인 하는 Microsoft 365 조직의 사용자는 기본 Mobility and Security에서 등록으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="d1127-123">레코드를 설정 하는 데 도움이 필요 하세요?</span><span class="sxs-lookup"><span data-stu-id="d1127-123">Need help setting up the records?</span></span> <span data-ttu-id="d1127-124">도메인 등록 기관을 찾고, 등록자 이름을 선택 하 여 [도메인 연결을 위한 dns 레코드 추가](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)에 제공 된 목록에서 dns 레코드를 만드는 방법에 대 한 단계별 도움말로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="d1127-125">이러한 지침을 사용 하 여 [AZURE AD Premium 없이 Windows 등록을 단순화](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)하는 방법에 설명 된 CNAME 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="d1127-126">두 CNAME 레코드를 추가한 후에는 보안 & 준수 센터로 돌아간 후 **데이터 손실 방지**  >  **장치 관리**로 이동   하 여 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="d1127-127">2 단계: (필수) iOS 장치용 APNs 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="d1127-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="d1127-128">IPad 및 Iphone와 같은 iOS 장치를 관리 하려면 APNs 인증서를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="d1127-129">전역 관리자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-129">Sign in to  Microsoft 365 with your global admin account.</span></span>   

2. <span data-ttu-id="d1127-130">브라우저에서 다음을 입력  [https://protection.office.com](https://protection.office.com/) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>  

3. <span data-ttu-id="d1127-131"> *\*데이터 손실 방지**   >  *\*장치 관리*\*를 선택 하 고 *\*iOS 장치용 APNs 인증서*\*를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-131">Select **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>   

4. <span data-ttu-id="d1127-132">Apple 푸시 알림 인증서 설정 페이지에서 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>  

5. <span data-ttu-id="d1127-133"> *\*CSR 파일 다운로드**   를 선택 하 고 사용자 컴퓨터의 원하는 위치에 인증서 서명 요청을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="d1127-134"> *\*다음*\*을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-134">Select **Next**.</span></span>
    
6. <span data-ttu-id="d1127-135">APNs 인증서 만들기 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-135">On the Create an APNs certificate page:</span></span>
    
    - <span data-ttu-id="d1127-136">Apple APNS Portal을 선택 하 여 Apple Push Certificate Portal을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    - <span data-ttu-id="d1127-137">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="d1127-137">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="d1127-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="d1127-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    - <span data-ttu-id="d1127-140">인증서 만들기 및 사용 약관에 동의를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-140">Select Create a Certificate and accept the Terms of Use.</span></span>
    
    - <span data-ttu-id="d1127-141">Browseto Microsoft 365 및 selectUpload에서 컴퓨터로 다운로드 한 인증서 서명 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-141">Browseto the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
    
    - <span data-ttu-id="d1127-142">Apple Push Certificate Portal에서 만든 APN 인증서를 컴퓨터로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-142">Downloadthe APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

    >[!TIP]
    ><span data-ttu-id="d1127-143">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="d1127-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="d1127-144">Microsoft 365으로 돌아가 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-144">Go back to Microsoft 365 and select **Next**.</span></span>   

8. <span data-ttu-id="d1127-145"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="d1127-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>   

9. <span data-ttu-id="d1127-146">  \*\*마침을\*\*선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-146">Select  **Finish**.</span></span>  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="d1127-147">3 단계: (권장) multi-factor authentication 설정</span><span class="sxs-lookup"><span data-stu-id="d1127-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="d1127-148">MFA는 두 번째 형태의 인증을 요구 하 여 모바일 장치 등록을 위해 Microsoft 365에 로그인 하는 기능을 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="d1127-149">사용자는 회사 계정 암호를 올바르게 입력 한 후에 모바일 장치에서 전화 통화, 문자 메시지 또는 앱 알림을 승인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="d1127-150">이 두 번째 인증 형식이 완료 된 후에만 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="d1127-151">사용자 장치를 기본 Mobility and Security에 등록 하면 사용자는 자신의 회사 계정만 사용 하 여 Microsoft 365 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="d1127-152">Azure AD 포털에서 MFA를 설정 하는 방법에 대 한 자세한 내용은 [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1127-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>

<span data-ttu-id="d1127-153">MFA를 설정한 후 보안 & 준수 센터로 돌아간 후 **데이터 손실 방지**   >  **장치 관리**   >  **장치 정책**으로 이동   하 여 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-153">After you set up MFA, go back to the Security & Compliance Center and navigate to **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="d1127-154">4 단계: (권장) 장치 보안 정책 관리</span><span class="sxs-lookup"><span data-stu-id="d1127-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="d1127-155">다음 단계에서는 Microsoft 365 조직 데이터를 보호 하는 데 도움이 되는 장치 보안 정책을 만들고 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="d1127-156">예를 들어, 사용자가 장치를 분실 한 경우, 5 분 동안 비활성 상태에서 장치를 잠그는 정책을 만들어 장치가 손실 되 면 데이터 손실을 방지할 수 있습니다 (로그인 오류 3 회).</span><span class="sxs-lookup"><span data-stu-id="d1127-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="d1127-157">전역 관리자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-157">Sign in to Microsoft 365 with your global admin account.</span></span> 

2. <span data-ttu-id="d1127-158"> [모바일 장치 관리 활성화](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="d1127-159">서비스가 활성화 되 면 인증 단계 대신 [장치 관리](https://admin.microsoft.com/adminportal/home#/MifoDevices)링크가 표시 됩니다   .</span><span class="sxs-lookup"><span data-stu-id="d1127-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>
    
3. <span data-ttu-id="d1127-160"> *\*장치 정책*\*으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-160">Go to **Device policies**.</span></span>

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 보안 및 이동성 정책 설정":::

4. <span data-ttu-id="d1127-162"> [기본 이동성 및 보안에서 장치 보안 정책 만들기](create-device-security-policies-in-basic-mmobility-and-security.md)의 단계에 따라 조직에 적합 한 장치 보안 정책을 만들고 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies-in-basic-mmobility-and-security.md).</span></span>

>[!TIP]
    - <span data-ttu-id="d1127-163">새 정책을 만들 때는 액세스를 허용 하 고 사용자 장치가 정책을 준수 하지 않는 정책 위반을 보고 하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="d1127-164">이를 통해 Microsoft 365에 대 한 액세스를 차단 하지 않고 정책의 영향을 받는 모바일 장치 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365 .</span></span><br/><span data-ttu-id="d1127-165">-조직의 모든 사람에 게 새 정책을 배포 하기 전에 소수의 사용자가 사용 하는 장치에서이를 테스트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-165">- Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span><br/><span data-ttu-id="d1127-166">-정책을 배포 하기 전에 조직에서 기본 이동성 및 보안의 장치 등록에 대 한 잠재적인 영향을 알 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-166">- Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="d1127-167">정책을 설정 하는 방법에 따라 정책 (비규격 장치)을 준수 하지 않는 장치는 Microsoft 365에 액세스 하지 못하도록 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="d1127-168">비규격 장치에는 장치를 초기화 하는 경우 등록 된 장치에서 삭제할 수 있는 앱, 사진 및 기타 개인 정보가 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="d1127-169">자세한 내용은 [기본 Mobility And Security에서 모바일 장치 초기화](wipe-mobile-device.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1127-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>
    
## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="d1127-170">사용자가 자신의 장치를 등록 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="d1127-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="d1127-171">모바일 장치 관리 정책을 만들고 배포한 후에는 다음에 모바일 장치에서 Microsoft 365에 로그인 할 때 장치 정책이 적용 되는 조직의 라이선스 Microsoft 365 사용자가 등록 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="d1127-172">Microsoft 365 전자 메일 및 문서에 액세스 하려면 먼저 등록 및 정품 인증 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="d1127-173">자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device-using-basic-mobility-and-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1127-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="d1127-174">등록 프로세스에서 사용자의 기본 설정 언어를 지원 하지 않는 경우 사용자는 모바일 장치에서 다른 언어로 등록 알림 및 단계를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="d1127-175">Microsoft 365에서 지원 되는 일부 언어는 현재 모바일 장치에서 등록 프로세스에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="d1127-176">Android 또는 iOS 장치를 사용 하는 사용자는 등록 프로세스의 일부로 회사 포털 앱을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1127-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1127-177">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d1127-177">Related Topics</span></span>

[<span data-ttu-id="d1127-178">기본 이동성 및 보안 기능</span><span class="sxs-lookup"><span data-stu-id="d1127-178">Capabilities of Basic Mobility and Security</span></span>](capabilities-of-basic-mobility-and-secruity.md)<br/>
[<span data-ttu-id="d1127-179">기본 모바일 및 보안에서 장치 보안 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d1127-179">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies-in-basic-mmobility-and-security.md)