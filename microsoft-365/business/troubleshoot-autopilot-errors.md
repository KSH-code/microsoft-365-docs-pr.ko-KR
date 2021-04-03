---
title: AutoPilot 장치 오류 문제 해결
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Microsoft 365 Business Premium에서 AutoPilot 장치 파일로 작업하는 동안 발생할 수 있는 오류를 해결하는 방법을 알아보습니다.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578090"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="a8325-103">AutoPilot 장치 오류 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a8325-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="a8325-104">장치 파일 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="a8325-104">Device file error messages</span></span>

<span data-ttu-id="a8325-105">다음은 Microsoft 365 Business Premium에서 AutoPilot 장치 파일로 작업하는 동안 발생할 수 있는 몇 가지 오류에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="a8325-106">**오류 코드**</span><span class="sxs-lookup"><span data-stu-id="a8325-106">**Error code**</span></span>|<span data-ttu-id="a8325-107">**해결 방법**</span><span class="sxs-lookup"><span data-stu-id="a8325-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8325-108">잘못된 요청 본문</span><span class="sxs-lookup"><span data-stu-id="a8325-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="a8325-109">이 오류가 발생하는 경우 이 오류는 거의 발생하지 않습니다. 작업을 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8325-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="a8325-110">장치에 대한 하드웨어 해시 값이 정확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="a8325-111">이 오류가 표시될 경우 한 장치의 하드웨어 해시에 대해 CSV 파일에서 제공한 값이 올바를 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="a8325-112">먼저 값이 올바르게 입력된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="a8325-113">값이 올 맞지만 이 오류가 계속 발생하면 하드웨어 공급업체에 도움을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a8325-114">다른 테넌트에 할당된 장치</span><span class="sxs-lookup"><span data-stu-id="a8325-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="a8325-115">이 오류가 표시될 경우 CSV 파일에서 하나 이상의 디바이스의 제품 키 또는 일련 번호에 대해 제공한 값이 올바를 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="a8325-116">먼저 값이 올바르게 입력된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="a8325-117">값이 올 맞지만 이 오류가 계속 발생하면 하드웨어 공급업체에 도움을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a8325-118">CSV 파일에 잘못된 일련 번호 또는 제품 키가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="a8325-119">이 오류가 표시되어도 등록하려는 장치가 이미 다른 조직에 의해 등록되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="a8325-120">이 오류를 해결하기 위해 하드웨어 공급업체에 도움을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a8325-121">이 장치는 AutoPilot을 사용하여 설치에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="a8325-122">이 오류는 장치가 AutoPilot 배포 요구 사항을 충족하지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="a8325-123">장치가 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="a8325-124">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="a8325-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="a8325-125">Windows에서 바로 사용할 수 있는 환경을 통해 제공되지 않은 새 장치.</span><span class="sxs-lookup"><span data-stu-id="a8325-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="a8325-126">장치를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-126">Device not found</span></span>  <br/> |<span data-ttu-id="a8325-127">이 오류는 CSV 파일의 하나 이상의 장치가 조직에 등록되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="a8325-128">이 문제를 해결하기 위해 하드웨어 공급업체에 도움을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a8325-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
