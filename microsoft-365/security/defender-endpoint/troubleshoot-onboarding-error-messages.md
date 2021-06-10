---
title: 온보더링 문제 및 오류 메시지 문제 해결
description: 끝점용 Microsoft Defender 설정을 완료하는 동안 온보딩 문제 및 오류 메시지를 해결합니다.
keywords: 문제 해결, 문제 해결, Azure Active Directory, 온보딩, 오류 메시지, 오류 메시지, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: b8e15f27ffe4babe730870fb576980c62cb0fd59
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844039"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="a9550-104">구독 및 포털 액세스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a9550-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9550-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a9550-105">**Applies to:**</span></span>
- [<span data-ttu-id="a9550-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a9550-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9550-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9550-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a9550-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a9550-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a9550-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="a9550-110">이 페이지에서는 끝점용 Microsoft Defender 서비스를 설정할 때 발생할 수 있는 문제를 해결하기 위한 자세한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="a9550-111">오류 메시지가 표시될 경우 Microsoft Defender 보안 센터 관련 링크가 제공될 문제 및 관련 링크에 대한 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="a9550-112">구독을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="a9550-112">No subscriptions found</span></span>

<span data-ttu-id="a9550-113">액세스하는 동안 Microsoft Defender 보안 센터 구독을 찾을  수 없음 메시지가 표시되어 있는 경우 사용자를 포털에 로그인하는 데 사용되는 Azure Active Directory(Azure AD)에 끝점용 Microsoft Defender 라이선스가 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="a9550-114">가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="a9550-114">Potential reasons:</span></span>
- <span data-ttu-id="a9550-115">Windows E5 및 Office E5 라이선스는 별도의 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="a9550-116">라이선스를 구매했지만 이 Azure AD 인스턴스에 프로비전되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="a9550-117">라이선스 프로비저닝 문제일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="a9550-118">서비스에 대한 인증에 사용되는 라이선스와 다른 Microsoft Azure AD 라이선스를 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="a9550-119">두 경우 모두 일반 Microsoft [Defender for Endpoint 지원](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) 또는 볼륨 라이선스 지원 에서 Microsoft 지원에 [문의해야 합니다.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)</span><span class="sxs-lookup"><span data-stu-id="a9550-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![구독을 찾을 수 없는 이미지](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="a9550-121">구독이 만료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-121">Your subscription has expired</span></span>

<span data-ttu-id="a9550-122">구독에 액세스하는 Microsoft Defender 보안 센터 **만료된** 메시지가 표시되면 온라인 서비스 구독이 만료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="a9550-123">다른 온라인 서비스 구독과 마찬가지로 Endpoint용 Microsoft Defender 구독에는 만료 날짜가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="a9550-124">특정 시점에 라이선스를 갱신하거나 연장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="a9550-125">만료 날짜 후 포털에 액세스할  때 라이선스를 갱신하지 않을 경우 구독이 만료된 메시지에 장치 등록 취소 패키지를 다운로드하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="a9550-126">보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="a9550-127">장치에 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="a9550-128">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![구독이 만료된 이미지](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="a9550-130">포털에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="a9550-131">포털에 액세스할 수 있는 권한이 없는 경우 끝점용 Microsoft Defender는 보안 모니터링, 인시던트 조사 및 대응 제품으로, 이에 따라 액세스가 제한되고 사용자가 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="a9550-132">자세한 내용은 포털에 [**대한 사용자 액세스 할당을 참조하세요.**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="a9550-132">For more information, see, [**Assign user access to the portal**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![포털 액세스 권한이 부여되지 않은 이미지](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="a9550-134">현재 포털의 일부 섹션에서 데이터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="a9550-135">포털 대시보드 및 기타 섹션에 "현재 데이터를 사용할 수 없습니다."라는 오류 메시지가 표시되는 경우:</span><span class="sxs-lookup"><span data-stu-id="a9550-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![현재 사용할 수 없는 데이터 이미지](images/atp-data-not-available.png)

<span data-ttu-id="a9550-137">그 아래에 있는 모든 하위omain을 허용해야 `securitycenter.windows.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="a9550-138">예를 들면 `*.securitycenter.windows.com`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="a9550-139">포털 통신 문제</span><span class="sxs-lookup"><span data-stu-id="a9550-139">Portal communication issues</span></span>
<span data-ttu-id="a9550-140">포털 액세스, 데이터 누락 또는 포털 일부에 대한 제한된 액세스와 관련한 문제가 발생하는 경우 다음 URL이 통신에 허용되고 열려 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9550-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



