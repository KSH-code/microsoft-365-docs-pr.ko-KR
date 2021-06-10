---
title: 엔드포인트 감지를 위해 Microsoft Defender를 끌어오도록 마이크로 포커스 ArcSight 구성
description: 마이크로 포커스 ArcSight를 구성하여 검색된 정보를 수신하고 끌어오도록 Microsoft Defender 보안 센터
keywords: Micro Focus ArcSight 구성, 보안 정보 및 이벤트 관리 도구, arcsight 구성
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166188"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="6da54-104">엔드포인트 감지를 위해 Defender를 끌어오도록 마이크로 포커스 ArcSight 구성</span><span class="sxs-lookup"><span data-stu-id="6da54-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6da54-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6da54-105">**Applies to:**</span></span>
- [<span data-ttu-id="6da54-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6da54-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6da54-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6da54-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="6da54-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6da54-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6da54-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="6da54-110">일부 파일 및 도구를 설치하고 구성하여 마이크로 포커스 ArcSight를 사용하여 끝점 감지를 위해 Defender를 끌어와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="6da54-111">[Endpoint용 Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="6da54-112">[Endpoint 검색용 Defender는](api-portal-mapping.md) 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6da54-113">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6da54-113">Before you begin</span></span>

<span data-ttu-id="6da54-114">Micro Focus ArcSight 커넥터 도구를 구성하려면 AAD(Micro Focus ArcSight Connector) 응용 프로그램에서 검색을 끌어 Azure Active Directory 구성 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="6da54-115">이 섹션에서는 필요한 구성 파일을 올바르게 설정하고 사용하는 데 필요한 정보를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="6da54-116">사용자 설정 메뉴에서 SIEM 통합 기능을 사용하도록 **설정해야 설정** 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="6da54-117">자세한 내용은 [Endpoint용 Defender에서 SIEM 통합 사용 을 참조하세요.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="6da54-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="6da54-118">SIEM 통합 기능을 사용하도록 설정하여 저장한 파일을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="6da54-119">다음 값을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="6da54-120">OAuth 2.0 토큰 새로 고침 URL</span><span class="sxs-lookup"><span data-stu-id="6da54-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="6da54-121">OAuth 2.0 클라이언트 ID</span><span class="sxs-lookup"><span data-stu-id="6da54-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="6da54-122">OAuth 2.0 클라이언트 비밀</span><span class="sxs-lookup"><span data-stu-id="6da54-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="6da54-123">다음 구성 파일을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="6da54-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="6da54-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="6da54-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="6da54-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="6da54-126">조직에서 사용하는 SIEM .zip 마이크로 포커스 ArcSight를 선택한 경우 이러한 두 파일이 포함된 파일 형식을 저장한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="6da54-127">다음 토큰을 생성하고 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="6da54-128">액세스 토큰</span><span class="sxs-lookup"><span data-stu-id="6da54-128">Access token</span></span>
  - <span data-ttu-id="6da54-129">새로 고침 토큰</span><span class="sxs-lookup"><span data-stu-id="6da54-129">Refresh token</span></span>

  <span data-ttu-id="6da54-130">포털의 **SIEM** 통합 설정 섹션에서 이러한 토큰을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="6da54-131">마이크로 포커스 ArcSight FlexConnector 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="6da54-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="6da54-132">다음 단계에서는 시작하기 전에의 모든 필수 단계를 [완료했다고 가정합니다.](#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="6da54-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="6da54-133">FlexConnector 설치 Windows 최신 32비트 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="6da54-134">HPE 소프트웨어 센터에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="6da54-135">이 도구는 일반적으로 다음과 같은 기본 위치에 `C:\Program Files\ArcSightFlexConnectors\current\bin` 설치됩니다. .</span><span class="sxs-lookup"><span data-stu-id="6da54-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="6da54-136">C: \current\bin과 같은 도구를 저장할 위치를 선택할 수 \\ *있습니다folder_location*\current\bin은 folder_location 위치를 나타내는 위치입니다. </span><span class="sxs-lookup"><span data-stu-id="6da54-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="6da54-137">다음 작업을 수행하여 설치 마법사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="6da54-138">소개</span><span class="sxs-lookup"><span data-stu-id="6da54-138">Introduction</span></span>
   - <span data-ttu-id="6da54-139">폴더 설치 선택</span><span class="sxs-lookup"><span data-stu-id="6da54-139">Choose Install Folder</span></span>
   - <span data-ttu-id="6da54-140">설치 집합 선택</span><span class="sxs-lookup"><span data-stu-id="6da54-140">Choose Install Set</span></span>
   - <span data-ttu-id="6da54-141">바로 가기 폴더 선택</span><span class="sxs-lookup"><span data-stu-id="6da54-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="6da54-142">사전 설치 요약</span><span class="sxs-lookup"><span data-stu-id="6da54-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="6da54-143">설치 중...</span><span class="sxs-lookup"><span data-stu-id="6da54-143">Installing...</span></span>

   <span data-ttu-id="6da54-144">이러한 각 작업에 대한 기본값을 유지하거나 요구 사항에 맞게 선택을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="6da54-145">파일 탐색기를 열고 SIEM 통합 기능을 사용하도록 설정한 경우 저장한 두 구성 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="6da54-146">두 파일을 FlexConnector 설치 위치에 저장합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="6da54-147">WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="6da54-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="6da54-148">WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="6da54-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="6da54-149">이 위치에 구성 파일을 넣어야 *합니다.* 여기서 folder_location 도구를 설치한 위치를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="6da54-150">핵심 커넥터 설치가 완료되면 커넥터 설치 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="6da54-151">커넥터 설정 창에서 **커넥터 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="6da54-152">유형: **ArcSight FlexConnector REST를 선택하고** 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="6da54-153">매개 변수 세부 정보 양식에 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="6da54-154">양식의 다른 모든 값은 선택 사항이며 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="6da54-155">필드</span><span class="sxs-lookup"><span data-stu-id="6da54-155">Field</span></span></th>
    <th><span data-ttu-id="6da54-156">값</span><span class="sxs-lookup"><span data-stu-id="6da54-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="6da54-157">구성 파일</span><span class="sxs-lookup"><span data-stu-id="6da54-157">Configuration File</span></span></td>
    <td><span data-ttu-id="6da54-158">클라이언트 속성 파일의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-158">Type in the name of the client property file.</span></span> <span data-ttu-id="6da54-159">이름은 다운로드한 파일에서 제공한 .zip 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="6da54-160">예를 들어 flexagent 디렉터리의 구성 파일 이름이 &quot; &quot; &quot; onparser.properties에WDATP-Connector.js경우 &quot; &quot; WDATP-Connector를 클라이언트 속성 파일의 이름으로 &quot; 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="6da54-161">이벤트 URL</span><span class="sxs-lookup"><span data-stu-id="6da54-161">Events URL</span></span></td>
    <td><span data-ttu-id="6da54-162">데이터 센터의 위치에 따라 EU 또는 미국 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="6da54-163"><b>EU의</b>경우 : <i></i> https:// wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="6da54-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="6da54-164"><b>미국:</b> <i></i> https:// wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="6da54-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="6da54-165"><b>영국</b>: https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="6da54-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="6da54-166">인증 유형</span><span class="sxs-lookup"><span data-stu-id="6da54-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="6da54-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="6da54-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="6da54-168">OAuth 2 클라이언트 속성 파일</span><span class="sxs-lookup"><span data-stu-id="6da54-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="6da54-169"><em>wdatp-connector.properties</em> 파일의 위치로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="6da54-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="6da54-170">이름은 다운로드한 파일에서 제공한 .zip 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="6da54-171">새로 고침 토큰</span><span class="sxs-lookup"><span data-stu-id="6da54-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="6da54-172"><b>SIEM</b> 설정 페이지에서 새로 고침 토큰을 생성하거나 restutil 도구를 사용하여 두 가지 방법으로 새로 고침 토큰을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="6da54-173">기본 설정에서 새로 고침 토큰을 생성하는 데 대한 자세한 내용은 <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint을 참조하세요.</a> <b></b></span><span class="sxs-lookup"><span data-stu-id="6da54-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="6da54-174"><b>restutil 도구를 사용하여 새로 고침 토큰을 얻다.</b> </span><span class="sxs-lookup"><span data-stu-id="6da54-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="6da54-175">a.</span><span class="sxs-lookup"><span data-stu-id="6da54-175">a.</span></span> <span data-ttu-id="6da54-176">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-176">Open a command prompt.</span></span> <span data-ttu-id="6da54-177">C:\ folder_location<em></em>\current\bin으로 folder_location <em></em> 도구를 설치한 위치를 나타내는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="6da54-178">b.</span><span class="sxs-lookup"><span data-stu-id="6da54-178">b.</span></span> <span data-ttu-id="6da54-179">Bin <code>arcsight restutil token -config</code> 디렉터리에서 입력합니다. 예를 들어 <b>arcsight restutil boxtoken -proxy</b> proxy.location.hp.com:8080 브라우저 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="6da54-180">c.</span><span class="sxs-lookup"><span data-stu-id="6da54-180">c.</span></span> <span data-ttu-id="6da54-181">자격 증명을 입력한 다음 암호 필드를 클릭하여 페이지가 리디렉션될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="6da54-182">로그인 프롬프트에 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="6da54-183">d.</span><span class="sxs-lookup"><span data-stu-id="6da54-183">d.</span></span> <span data-ttu-id="6da54-184">새로 고침 토큰이 명령 프롬프트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="6da54-185">e.</span><span class="sxs-lookup"><span data-stu-id="6da54-185">e.</span></span> <span data-ttu-id="6da54-186">복사하여 새로 고침 토큰 <b>필드에 붙여 넣습니다.</b></span><span class="sxs-lookup"><span data-stu-id="6da54-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="6da54-187">브라우저 창이 커넥터에 의해 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="6da54-188">응용 프로그램 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-188">Login with your application credentials.</span></span> <span data-ttu-id="6da54-189">로그인한 후 OAuth2 클라이언트에 대한 권한을 부여할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="6da54-190">커넥터 구성이 인증될 수 있도록 OAuth 2 클라이언트에 대한 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="6da54-191">https URL인 경우 로컬 호스트의 <code>redirect_uri</code> URL로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="6da54-192">로컬 호스트에서 실행되는 커넥터에서 제공한 인증서를 신뢰해야 하는 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="6da54-193">https가 https인 redirect_uri 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="6da54-194">그러나 웹 응용 redirect_uri URL을 지정하는 경우 인증서 신뢰에 동의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="6da54-195">마이크로 포커스 ArcSight 커넥터 설정 창으로 돌아가서 커넥터 설정을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="6da54-196">**대상으로 ArcSight Manager(암호화)를** 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="6da54-197">관리자 호스트 이름의 대상 IP/호스트 이름을 입력하고 매개 변수 양식에 자격 증명을 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="6da54-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="6da54-198">양식의 다른 모든 값은 기본값으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="6da54-199">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-199">Click **Next**.</span></span>

11. <span data-ttu-id="6da54-200">커넥터 세부 정보 양식에 커넥터 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="6da54-201">양식의 다른 모든 값은 선택 사항이며 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="6da54-202">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-202">Click **Next**.</span></span>

12. <span data-ttu-id="6da54-203">ESM 관리자 인증서 가져오기 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="6da54-204">대상에서 커넥터로 인증서 **가져오기 를 선택하고** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="6da54-205">커넥터 **추가 요약** 창이 표시되고 인증서를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="6da54-206">커넥터 추가 요약 창의 세부 **정보가** 올바른지 확인한 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="6da54-207">서비스로 **설치를 선택하고** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="6da54-208">서비스 내부 이름 **필드에 이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="6da54-209">양식의 다른 모든 값은 기본값으로 유지하거나 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="6da54-210">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-210">Click **Next**.</span></span>

16. <span data-ttu-id="6da54-211">서비스 매개 변수를 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="6da54-212">서비스 설치 요약 **창이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="6da54-213">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-213">Click **Next**.</span></span>

17. <span data-ttu-id="6da54-214">끝내기 및 다음 **을** 선택하여 설치를 **완료합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="6da54-215">마이크로 포커스 ArcSight 콘솔 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="6da54-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="6da54-216">다음 작업을 수행하여 설치 마법사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="6da54-217">소개</span><span class="sxs-lookup"><span data-stu-id="6da54-217">Introduction</span></span>
   - <span data-ttu-id="6da54-218">사용권 계약</span><span class="sxs-lookup"><span data-stu-id="6da54-218">License Agreement</span></span>
   - <span data-ttu-id="6da54-219">특별 알림</span><span class="sxs-lookup"><span data-stu-id="6da54-219">Special Notice</span></span>
   - <span data-ttu-id="6da54-220">ArcSight 설치 디렉터리 선택</span><span class="sxs-lookup"><span data-stu-id="6da54-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="6da54-221">바로 가기 폴더 선택</span><span class="sxs-lookup"><span data-stu-id="6da54-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="6da54-222">사전 설치 요약</span><span class="sxs-lookup"><span data-stu-id="6da54-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="6da54-223">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-223">Click **Install**.</span></span> <span data-ttu-id="6da54-224">설치가 완료되면 ArcSight 콘솔 구성 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="6da54-225">관리자 호스트 이름에 **localhost를** 입력하고 관리자 포트에 8443을 **입력한** 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="6da54-226">직접 **연결 사용을 선택하고** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="6da54-227">암호 **기반 인증을 선택하고** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="6da54-228">단일 **사용자 설치를 선택합니다. (권장)** 를 클릭한 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="6da54-229">**완료를** 클릭하여 설치 관리자를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="6da54-230">마이크로 포커스 ArcSight 콘솔에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="6da54-231">활성 채널 **집합 새**  >  **조건 장치** 장치  >    >  **제품으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="6da54-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="6da54-232">장치 **제품 설정 = Microsoft Defender ATP.**</span><span class="sxs-lookup"><span data-stu-id="6da54-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="6da54-233">이벤트가 도구로 흐르고 있는 것이 확인되면 프로세스를 다시 중지하고 Windows 서비스로 이동하고 ArcSight FlexConnector REST를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="6da54-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="6da54-234">이제 마이크로 포커스 ArcSight 콘솔에서 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="6da54-235">끝점 검색에 대한 Defender는 공급업체로 "Microsoft"를, 장치 이름으로 "Windows Defender ATP"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="6da54-236">마이크로 포커스 ArcSight 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6da54-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="6da54-237">**문제:** 토큰을 새로 고치지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="6da54-238">C: folder_location \\ \current\logs에 있는 로그를 찾을  수 folder_location 도구를 설치한 위치를 나타내는 로그를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="6da54-239">_agent.log를 열고_ 을 찾아 을 찾아야 `ERROR/FATAL/WARN` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="6da54-240">**증상:** 다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="6da54-241">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="6da54-241">**Solution:**</span></span>

1. <span data-ttu-id="6da54-242">커넥터 창에서 Ctrl + C를 클릭하여 프로세스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="6da54-243">**"일괄 처리 작업 종료 Y/N?"을** 요청하면 Y를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="6da54-244">WDATP-connector.properties 파일을 저장한 폴더로 이동한 후 편집하여 다음 값을 `reauthenticate=true` 추가합니다. .</span><span class="sxs-lookup"><span data-stu-id="6da54-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="6da54-245">다음 명령을 실행하여 커넥터를 다시 `arcsight.bat connectors` 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="6da54-246">브라우저 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-246">A browser window appears.</span></span> <span data-ttu-id="6da54-247">실행을 허용하면 사라지고 커넥터가 실행 중이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="6da54-248">프로세스를 다시 중지하여 커넥터가 실행되고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="6da54-249">그런 다음 커넥터를 다시 시작하면 브라우저 창이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6da54-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6da54-250">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6da54-250">Related topics</span></span>
- [<span data-ttu-id="6da54-251">Endpoint용 Defender에서 SIEM 통합 사용</span><span class="sxs-lookup"><span data-stu-id="6da54-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="6da54-252">SIEM 도구로 검색 끌어오기</span><span class="sxs-lookup"><span data-stu-id="6da54-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="6da54-253">REST API를 사용하여 끝점 검색을 위한 Defender 끌어오기</span><span class="sxs-lookup"><span data-stu-id="6da54-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="6da54-254">SIEM 도구 통합 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6da54-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
