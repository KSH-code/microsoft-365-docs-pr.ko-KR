---
title: Android의 끝점용 Microsoft Defender 문제 해결
description: Android의 끝점용 Microsoft Defender 문제 해결
keywords: Microsoft, defender, atp, mde, android, 클라우드, 연결, 통신
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1a19582073565a958aab444541381f5772b6f4f1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687606"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="a7971-104">Android의 끝점용 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a7971-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a7971-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a7971-105">**Applies to:**</span></span>
- <span data-ttu-id="a7971-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="a7971-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="a7971-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7971-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a7971-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a7971-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a7971-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="a7971-110">장치를 등록할 때 앱이 설치된 후 로그인 문제가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="a7971-111">등록하는 동안 장치에 앱을 설치한 후 로그인 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="a7971-112">이 문서에서는 로그인 문제를 해결하기 위한 해결법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="a7971-113">로그인 실패 - 예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="a7971-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="a7971-114">**로그인 실패:** *예기치 않은 오류, 나중에 시도*</span><span class="sxs-lookup"><span data-stu-id="a7971-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![로그인 실패 오류의 이미지 예기치 않은 오류](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="a7971-116">**메시지:**</span><span class="sxs-lookup"><span data-stu-id="a7971-116">**Message:**</span></span>

<span data-ttu-id="a7971-117">예기치 않은 오류, 나중에 시도</span><span class="sxs-lookup"><span data-stu-id="a7971-117">Unexpected error, try later</span></span>

<span data-ttu-id="a7971-118">**원인:**</span><span class="sxs-lookup"><span data-stu-id="a7971-118">**Cause:**</span></span>

<span data-ttu-id="a7971-119">장치에 "Microsoft Authenticator" 앱의 이전 버전이 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="a7971-120">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="a7971-120">**Solution:**</span></span>

<span data-ttu-id="a7971-121">Google Play 스토어에서 최신 버전 [및 Microsoft Authenticator를](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) 설치하고 다시 시도</span><span class="sxs-lookup"><span data-stu-id="a7971-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="a7971-122">로그인 실패 - 잘못된 라이선스</span><span class="sxs-lookup"><span data-stu-id="a7971-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="a7971-123">**로그인 실패: 라이선스가** *잘못되었습니다. 관리자에게 문의하세요.*</span><span class="sxs-lookup"><span data-stu-id="a7971-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![로그인 실패 이미지 관리자에게 문의하시기 바랍니다.](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="a7971-125">**메시지:** *라이선스가 잘못되었습니다. 관리자에게 문의하세요.*</span><span class="sxs-lookup"><span data-stu-id="a7971-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="a7971-126">**원인:**</span><span class="sxs-lookup"><span data-stu-id="a7971-126">**Cause:**</span></span>

<span data-ttu-id="a7971-127">Microsoft 365 라이선스가 할당되지 않은 경우 또는 조직에 Microsoft 365 Enterprise 구독 라이선스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="a7971-128">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="a7971-128">**Solution:**</span></span>

<span data-ttu-id="a7971-129">관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7971-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="a7971-130">일부 OEM 장치에서 피싱 페이지가 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="a7971-131">**다음에 적용됩니다.** 특정 OEM만</span><span class="sxs-lookup"><span data-stu-id="a7971-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="a7971-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="a7971-132">**Xiaomi**</span></span>

<span data-ttu-id="a7971-133">Android용 끝점용 Defender에서 감지한 피싱 및 유해한 웹 위협은 일부 Xiaomi 장치에서 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="a7971-134">이러한 장치에서는 다음 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-134">The following functionality doesn't work on these devices.</span></span>

![안전하지 않은 것으로 보고된 사이트의 이미지](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="a7971-136">**원인:**</span><span class="sxs-lookup"><span data-stu-id="a7971-136">**Cause:**</span></span>

<span data-ttu-id="a7971-137">Xiaomi 장치에는 새로운 사용 권한 모델이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="a7971-138">이렇게 하면 Android용 Endpoint용 Defender가 백그라운드에서 실행되는 동안 팝업 창을 표시하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="a7971-139">Xiaomi 장치 권한: "백그라운드에서 실행되는 동안 팝업 창 표시"</span><span class="sxs-lookup"><span data-stu-id="a7971-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![팝업 설정 이미지](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="a7971-141">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="a7971-141">**Solution:**</span></span>

<span data-ttu-id="a7971-142">Xiaomi 디바이스에 대해 필요한 권한을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="a7971-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="a7971-143">백그라운드에서 실행되는 동안 팝업 창을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a7971-143">Display pop-up windows while running in the background.</span></span>
