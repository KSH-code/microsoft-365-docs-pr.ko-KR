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
description: 기본 이동성 및 보안을 설정하여 사용자의 모바일 장치를 보호하고 관리합니다.
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876867"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="b9a69-103">기본 이동성 및 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b9a69-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="b9a69-104">기본 제공 Microsoft 365용 Basic Mobility and Security는 iPhone, iPad, Androids 및 Windows 휴대폰과 같은 사용자의 모바일 장치를 보호하고 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="b9a69-105">디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="b9a69-106">질문이 있나요?</span><span class="sxs-lookup"><span data-stu-id="b9a69-106">Have questions?</span></span> <span data-ttu-id="b9a69-107">일반적인 질문을 해결하기 위한 FAQ는 기본 이동성 및 보안 FAQ(질문과 대답)를 [참조하세요.](frequently-asked-questions.md)</span><span class="sxs-lookup"><span data-stu-id="b9a69-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.md).</span></span> <span data-ttu-id="b9a69-108">위임된 관리자 계정을 사용하여 Basic Mobility and Security를 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="b9a69-109">자세한 내용은 [파트너: 위임된 관리 제공을 참조하세요.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)</span><span class="sxs-lookup"><span data-stu-id="b9a69-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="b9a69-110">장치 관리는 보안 & 준수 센터의 일부이기 때문에 기본 이동성 및 보안 설정을 시작하려면 이 센터로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off Basic Mobility and Security setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="b9a69-111">기본 모바일 및 보안 서비스 활성화</span><span class="sxs-lookup"><span data-stu-id="b9a69-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="b9a69-112">전역 관리자 계정으로 Microsoft 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-112">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="b9a69-113">기본 [이동성 및 보안 활성화로 이동 합니다.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="b9a69-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>

   <span data-ttu-id="b9a69-114">기본 이동성 및 보안을 활성화하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="b9a69-115">완료되면 다음 단계를 설명하는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="b9a69-116">모바일 장치 관리 설정</span><span class="sxs-lookup"><span data-stu-id="b9a69-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="b9a69-117">서비스가 준비되면 다음 단계를 완료하여 설치를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a><span data-ttu-id="b9a69-118">1단계: (필수) 기본 이동성 및 보안에 대한 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="b9a69-118">Step 1: (Required) Configure domains for Basic Mobility and Security</span></span>

<span data-ttu-id="b9a69-119">Microsoft 365와 연결된 사용자 지정 도메인이 없는 경우 또는 Windows 장치를 관리하지 않는 경우 이 섹션을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="b9a69-120">그렇지 않으면 DNS 호스트에서 도메인에 대한 DNS 레코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="b9a69-121">Microsoft 365에서 도메인을 설정하는 일부로 레코드를 이미 추가한 경우 모두 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="b9a69-122">레코드를 추가하면 사용자 지정 도메인을 사용하는 전자 메일 주소로 Windows 장치에 로그인하는 조직의 Microsoft 365 사용자가 기본 이동성 및 보안에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="b9a69-123">레코드 설정에 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="b9a69-123">Need help setting up the records?</span></span> <span data-ttu-id="b9a69-124">도메인 등록 기관을 찾고 등록 기관 이름을 선택하여 도메인을 연결하기 위해 DNS 레코드 추가에 제공된 목록에서 DNS 레코드를 만들기 위한 단계별 [도움말로 이동하십시오.](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)</span><span class="sxs-lookup"><span data-stu-id="b9a69-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="b9a69-125">이러한 지침을 사용하여 Azure AD Premium 없이 Windows 등록 간소화에 설명된 CNAME [레코드를 만들 수 있습니다.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)</span><span class="sxs-lookup"><span data-stu-id="b9a69-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="b9a69-126">두 개의 CNAME 레코드를 추가한 후 보안 & 준수 센터로 돌아가서 데이터 손실 방지 장치 관리로 이동하여 다음 단계를  >     완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="b9a69-127">2단계: (필수) iOS 장치에 대한 APNS 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="b9a69-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="b9a69-128">iPad 및 iPhone과 같은 iOS 장치를 관리하려면 APNS 인증서를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="b9a69-129">전역 관리자 계정으로 Microsoft 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-129">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="b9a69-130">브라우저 유형:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="b9a69-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="b9a69-131">데이터  **손실 방지 장치** 관리를 선택하고 iOS 장치에 대한   >  \*\*\*\* **APNS 인증서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9a69-131">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="b9a69-132">Apple 푸시 알림 인증서 설정 페이지에서 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9a69-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="b9a69-133"> *\*CSR 파일 다운로드를** 선택하고 기억할 수 있는 컴퓨터의 아무 곳에 인증서 서명   요청을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="b9a69-134">다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9a69-134">Select **Next**.</span></span>

6. <span data-ttu-id="b9a69-135">APNS 인증서 만들기 페이지에서 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-135">On the Create an APNs certificate page:</span></span>

   - <span data-ttu-id="b9a69-136">Apple APNS 포털을 선택하여 Apple 푸시 인증서 포털을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
   - <span data-ttu-id="b9a69-137">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="b9a69-137">Sign in with an Apple ID.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="b9a69-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="b9a69-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

   - <span data-ttu-id="b9a69-140">인증서 만들기를 선택하고 사용 약관에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-140">Select Create a Certificate and accept the Terms of Use.</span></span>
   - <span data-ttu-id="b9a69-141">Microsoft 365에서 컴퓨터에 다운로드한 인증서 서명 요청을 찾아서 selectUpload를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-141">Browse to the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
   - <span data-ttu-id="b9a69-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span><span class="sxs-lookup"><span data-stu-id="b9a69-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

     > [!TIP]
     > <span data-ttu-id="b9a69-143">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="b9a69-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="b9a69-144">Microsoft 365로 돌아가 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9a69-144">Go back to Microsoft 365 and select **Next**.</span></span>

8. <span data-ttu-id="b9a69-145"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="b9a69-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="b9a69-146">완료를  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9a69-146">Select  **Finish**.</span></span>

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="b9a69-147">3단계: (권장) 다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="b9a69-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="b9a69-148">MFA는 두 번째 형태의 인증을 요구하여 모바일 장치 등록을 위해 Microsoft 365에 로그인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="b9a69-149">사용자는 직장 계정 암호를 올바르게 입력한 후 모바일 장치에서 전화 통화, 문자 메시지 또는 앱 알림을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="b9a69-150">두 번째 인증 형식이 완료된 후에만 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="b9a69-151">기본 이동성 및 보안에 사용자 장치가 등록된 후 사용자는 자신의 작업 계정만 사용하여 Microsoft 365 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="b9a69-152">Azure AD 포털에서 MFA를 켜는 방법에 대한 자세한 내용은 다단계 인증 [설정을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=519255)</span><span class="sxs-lookup"><span data-stu-id="b9a69-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>

<span data-ttu-id="b9a69-153">MFA를 설정한 후 보안 & 준수 센터로 돌아가 \*\*\*\* 데이터 손실 방지 장치 관리 장치 정책으로 이동하여 다음   >     >  \*\*\*\*   단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-153">After you set up MFA, go back to the Security & Compliance Center and navigate to  **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="b9a69-154">4단계: (권장) 장치 보안 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b9a69-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="b9a69-155">다음 단계는 Microsoft 365 조직 데이터를 보호하는 데 도움이 되는 장치 보안 정책을 만들고 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="b9a69-156">예를 들어 5분 동안 비활성으로 장치를 잠그고 3회 로그인 실패 후 장치를 지우는 정책을 만들어 사용자가 장치를 분실할 경우 데이터 손실을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="b9a69-157">전역 관리자 계정으로 Microsoft 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-157">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="b9a69-158">모바일 [장치 관리 활성화를 선택합니다.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="b9a69-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="b9a69-159">서비스가 활성화된 경우 대신 정품 인증 단계에 장치 관리에 대한 [링크가 표시됩니다.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  </span><span class="sxs-lookup"><span data-stu-id="b9a69-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>

3. <span data-ttu-id="b9a69-160">장치 **정책으로 이동.**</span><span class="sxs-lookup"><span data-stu-id="b9a69-160">Go to **Device policies**.</span></span>

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 보안 및 모바일 정책 설정":::

4. <span data-ttu-id="b9a69-162">기본 이동성 및 보안에서 장치 보안 정책 만들기의 단계에 따라 조직에 적합한 장치 보안 정책을 [만들고 배포합니다.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b9a69-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

> [!TIP]
>
> - <span data-ttu-id="b9a69-163">새 정책을 만들 때 사용자 장치가 정책을 준수하지 않는 경우 액세스 및 보고 정책 위반을 허용하도록 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="b9a69-164">이렇게 하면 Microsoft 365에 대한 액세스를 차단하지 않고 정책의 영향을 미치는 모바일 장치 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365.</span></span>
>
> - <span data-ttu-id="b9a69-165">조직의 모든 사용자에게 새 정책을 배포하기 전에 소수의 사용자가 사용하는 장치에서 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-165">Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span>
>
> - <span data-ttu-id="b9a69-166">또한 정책을 배포하기 전에 조직에 기본 이동성 및 보안에서 장치 등록이 미칠 수 있는 영향을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-166">Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="b9a69-167">정책을 설정하는 방법에 따라 정책을 준수하지 않는 장치(비규준 장치)가 Microsoft 365에 액세스하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="b9a69-168">호환되지 않는 장치에는 앱이 설치되고, 사진 및 기타 개인 정보도 있을 수 있으며, 등록된 디바이스에서 장치가 지워진 경우 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="b9a69-169">자세한 내용은 기본 이동성 및 보안에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="b9a69-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="b9a69-170">사용자가 장치를 등록하는지 확인</span><span class="sxs-lookup"><span data-stu-id="b9a69-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="b9a69-171">모바일 장치 관리 정책을 만들어 배포한 후 장치 정책이 적용되는 조직의 사용이 허가된 각 Microsoft 365 사용자는 다음에 모바일 장치에서 Microsoft 365에 로그인할 때 등록 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="b9a69-172">Microsoft 365 전자 메일 및 문서에 액세스하려면 먼저 등록 및 정품 인증 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="b9a69-173">자세한 내용은 기본 이동성 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="b9a69-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9a69-174">사용자의 기본 설정 언어가 등록 프로세스에서 지원되지 않는 경우 사용자는 등록 알림 및 모바일 장치에서 다른 언어로 단계를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="b9a69-175">Microsoft 365에서 지원되는 모든 언어가 현재 모바일 장치에서 등록 프로세스에 지원되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="b9a69-176">Android 또는 iOS 장치를 사용 하는 사용자는 등록 프로세스의 일부로 회사 포털 앱을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a69-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9a69-177">관련 주제</span><span class="sxs-lookup"><span data-stu-id="b9a69-177">Related Topics</span></span>

[<span data-ttu-id="b9a69-178">기본 모바일 및 보안 기능</span><span class="sxs-lookup"><span data-stu-id="b9a69-178">Capabilities of Basic Mobility and Security</span></span>](capabilities.md)<br/>
[<span data-ttu-id="b9a69-179">기본 이동성 및 보안에서 장치 보안 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b9a69-179">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)