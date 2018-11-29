---
title: AutoPilot 장치 오류 문제 해결
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 작업을 자동화할 장치 파일 오류를 해결 하는 방법에 알아봅니다.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869899"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="ea1e8-103">AutoPilot 장치 오류 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ea1e8-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="ea1e8-104">장치 파일 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="ea1e8-104">Device file error messages</span></span>

<span data-ttu-id="ea1e8-105">오류 중 일부에 대해 다음 정보 Microsoft 365 비즈니스에서 작업을 자동화할 장치 파일을 사용 하는 동안 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="ea1e8-106">**오류 코드**</span><span class="sxs-lookup"><span data-stu-id="ea1e8-106">**Error code**</span></span>|<span data-ttu-id="ea1e8-107">**평가판을 수정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea1e8-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea1e8-108">잘못 된 요청 본문</span><span class="sxs-lookup"><span data-stu-id="ea1e8-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="ea1e8-109">이 오류를 표시 하는 경우 작업을 다시 시도이 오류는 거의 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="ea1e8-110">장치에 대 한 하드웨어 해시 값 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="ea1e8-p101">이 오류를 표시 하는 경우 하드웨어 해시는 하나의 장치에 대 한 CSV 파일에 제공 된 값이 틀리면는 것을 의미 합니다. 먼저, 값 올바르게 입력 했는지 확인 합니다. 값에 올바른, 이지만이 오류가 계속 발생 하는 경우 하드웨어 공급 업체에 문의 도움을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ea1e8-114">다른 테 넌 트에 할당 된 장치</span><span class="sxs-lookup"><span data-stu-id="ea1e8-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="ea1e8-p102">이 오류가 표시 되 면 일련번호 또는 하나 이상의 장치의 제품 키에 대 한 CSV 파일에 제공 된 값이 틀리면는 의미입니다. 먼저, 값 올바르게 입력 했는지 확인 합니다. 값에 올바른, 이지만이 오류가 계속 발생 하는 경우 하드웨어 공급 업체에 문의 도움을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ea1e8-118">CSV 파일에 잘못 된 일련번호 또는 제품 키 포함</span><span class="sxs-lookup"><span data-stu-id="ea1e8-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="ea1e8-p103">이 오류를 표시 하는 경우 tyring을 등록 하는 장치는 다른 조직에서 이미 등록 되어 것을 의미 합니다. 이 문제를 해결 하려면 하드웨어 공급 업체에 문의 도움 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ea1e8-121">작업을 자동화할을 사용 하 여 설치를 위해이 장치가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="ea1e8-p104">이 오류는 장치 작업을 자동화할 배포 요구 사항에 맞지 않는 것을 의미 합니다. 장치에서 이러한 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="ea1e8-124">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="ea1e8-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="ea1e8-125">Windows 첫 실행 경험을 완료하지 않은 새 장치</span><span class="sxs-lookup"><span data-stu-id="ea1e8-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="ea1e8-126">장치를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-126">Device not found</span></span>  <br/> |<span data-ttu-id="ea1e8-p105">이 오류는 CSV 파일에 하나 이상의 장치 조직에 등록 되지 않았음을 의미 합니다. 이 문제를 해결 하려면 하드웨어 공급 업체에 문의 도움 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1e8-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
