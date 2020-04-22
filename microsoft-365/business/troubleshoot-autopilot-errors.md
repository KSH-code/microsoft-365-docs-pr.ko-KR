---
title: AutoPilot 장치 오류 문제 해결
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Microsoft 365 Business Premium에서 AutoPilot 장치 파일을 사용 하 여 작업 하는 동안 발생할 수 있는 오류를 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: 0c0742e5bf17c85cedfb421cabfd87c0e2184ba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635047"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="1501f-103">AutoPilot 장치 오류 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1501f-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="1501f-104">장치 파일 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="1501f-104">Device file error messages</span></span>

<span data-ttu-id="1501f-105">다음은 Microsoft 365 Business Premium에서 AutoPilot 장치 파일을 사용 하 여 작업 하는 동안 발생할 수 있는 몇 가지 오류에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="1501f-106">**오류 코드**</span><span class="sxs-lookup"><span data-stu-id="1501f-106">**Error code**</span></span>|<span data-ttu-id="1501f-107">**해결 방법**</span><span class="sxs-lookup"><span data-stu-id="1501f-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1501f-108">요청 본문이 잘못 됨</span><span class="sxs-lookup"><span data-stu-id="1501f-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="1501f-109">이 오류가 표시 되는 경우는 거의 발생 하지 않는 경우에는 작업을 다시 시도 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1501f-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="1501f-110">장치에 대 한 하드웨어 해시 값이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="1501f-111">이 오류가 표시 되 면 한 장치의 하드웨어 해시에 대해 CSV 파일에 제공한 값이 잘못 되었음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="1501f-112">먼저 값을 올바르게 입력 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="1501f-113">값이 올바르지만이 오류가 여전히 발생 하는 경우에는 하드웨어 공급 업체에 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="1501f-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1501f-114">다른 테 넌 트에 할당 된 장치</span><span class="sxs-lookup"><span data-stu-id="1501f-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="1501f-115">이 오류가 표시 되는 경우에는 CSV 파일에서 하나 이상의 장치에 대 한 일련 번호나 제품 키에 제공한 값이 올바르지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="1501f-116">먼저 값을 올바르게 입력 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="1501f-117">값이 올바르지만이 오류가 여전히 발생 하는 경우에는 하드웨어 공급 업체에 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="1501f-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1501f-118">CSV 파일에 잘못 된 일련 번호 또는 제품 키가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="1501f-119">이 오류가 표시 되 면 등록 하려는 장치가 이미 다른 조직에서 등록 되었음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="1501f-120">이 오류를 해결 하려면 하드웨어 공급 업체에 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="1501f-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1501f-121">AutoPilot을 사용 하 여 설치를 지원 하지 않는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="1501f-122">이 오류는 장치가 AutoPilot 배포 요구 사항을 충족 하지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="1501f-123">장치가 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="1501f-124">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="1501f-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="1501f-125">Windows 기본 경험을 거치지 않은 새로운 장치</span><span class="sxs-lookup"><span data-stu-id="1501f-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="1501f-126">장치를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="1501f-126">Device not found</span></span>  <br/> |<span data-ttu-id="1501f-127">이 오류는 CSV 파일에 있는 하나 이상의 장치가 조직에 등록 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1501f-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="1501f-128">이 문제를 해결 하려면 하드웨어 공급 업체에 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="1501f-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
