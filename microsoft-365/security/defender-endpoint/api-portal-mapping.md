---
title: 끝점 검색 API 필드에 대한 Microsoft Defender
description: 검색 API 필드가 검색 API 필드의 값에 매핑되는 Microsoft 365 Defender
keywords: 검색, 검색 필드, 필드, api, 필드, 검색 끌어오기, rest api, 요청, 응답
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
ms.openlocfilehash: 3f3eef756d37bf1552120a05e351c844b37b863b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185932"
---
# <a name="microsoft-defender-for-endpoint-detections-api-fields"></a>끝점 검색 API 필드에 대한 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-apiportalmapping-abovefoldlink)

검색 API의 일부로 노출되는 데이터 필드와 이러한 필드가 검색 API에 매핑되는 방법을 Microsoft 365 Defender.

> [!NOTE]
>
> - [Endpoint용 Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.
> - **Microsoft Defender ATP 검색은** 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 **구성됩니다.**
> - 끝점 경고용 Microsoft Defender 경고 API는 경고 소비를 위한 최신 API로, 각 경고에 대한 자세한 관련 증거 목록을 포함 합니다. 자세한 내용은 [Alert 메서드](alerts.md) 및 속성 및 목록 [경고를 참조하세요.](get-alerts.md)

## <a name="detections-api-fields-and-portal-mapping"></a>검색 API 필드 및 포털 매핑

다음 표에는 검색 API 페이로드에 노출되는 사용 가능한 필드가 나열되어 있습니다. 채워진 값에 대한 예제와 포털에 데이터가 반영되는 방식에 대한 참조를 보여줍니다.

ArcSight 필드 열에는 끝점용 Defender 필드와 ArcSight의 기본 제공 필드 간의 기본 매핑이 포함되어 있습니다. SIEM 통합 기능을 사용하도록 설정하면 포털에서 매핑 파일을 다운로드할 수 있으며 조직의 요구에 따라 매핑 파일을 수정할 수 있습니다. 자세한 내용은 [Endpoint용 Defender에서 SIEM 통합 사용 을 참조하세요.](enable-siem-integration.md)

필드 번호는 아래 이미지의 번호와 일치합니다.

> [!div class="mx-tableFixed"]
>
> |포털 레이블|SIEM 필드 이름|ArcSight 필드|예제 값|설명|
> |---|---|---|---|---|
> |1|AlertTitle|name|Microsoft Defender AV에서 'Mikatz' 높은 심각도 맬웨어 검색|모든 검색에 사용할 수 있는 값입니다.|
> |2|심각도|deviceSeverity|높음|모든 검색에 사용할 수 있는 값입니다.|
> |3 |범주|deviceEventCategory|맬웨어|모든 검색에 사용할 수 있는 값입니다.|
> |4 |검색 원본|sourceServiceName|바이러스 검사|Microsoft Defender 바이러스 백신 또는 Defender for Endpoint. 모든 검색에 사용할 수 있는 값입니다.|
> |5 |MachineName|sourceHostName|desktop-4a5ngd6|모든 검색에 사용할 수 있는 값입니다.|
> |6 |FileName|fileName|Robocopy.exe|파일 또는 프로세스와 관련된 검색에 사용할 수 있습니다.|
> |7 |FilePath|filePath|C:\Windows\System32\Robocopy.exe|파일 또는 프로세스와 관련된 검색에 사용할 수 있습니다.|
> |8 |UserDomain|sourceNtDomain|CONTOSO|활동을 실행하는 사용자 컨텍스트의 도메인으로, 끝점 동작 기반 검색을 위해 Defender에 사용할 수 있습니다.|
> |9 |UserName|sourceUserName|liz.bean|활동을 실행하는 사용자 컨텍스트로, 끝점 동작 기반 검색을 위해 Defender에 사용할 수 있습니다.|
> |10 |Sha1|fileHash|3da065e07b990034e9db7842167f70b63aa5329|파일 또는 프로세스와 관련된 검색에 사용할 수 있습니다.|
> |11 |Sha256|deviceCustomString6|ebf54f745dc81e1958f75e4ca91dd0ab989fc9787bb6b0bf993e2f5|Microsoft Defender AV 감지에 사용할 수 있습니다.|
> |12 |Md5|deviceCustomString5|db979c04a99b96d370988325bb5a8b21|Microsoft Defender AV 감지에 사용할 수 있습니다.|
> |13|ThreatName|deviceCustomString1|HackTool:Win32/Mikatz!dha|Microsoft Defender AV 감지에 사용할 수 있습니다.|
> |14 |IpAddress|sourceAddress|218.90.204.141|네트워크 이벤트와 관련된 검색에 사용할 수 있습니다. 예를 들어 '악성 네트워크 대상에 대한 통신'을 들 수 있습니다.|
> |15 |Url|requestUrl|down.esales360.cn|네트워크 이벤트와 관련된 검색에 사용할 수 있습니다. 예를 들어 '악성 네트워크 대상에 대한 통신'을 들 수 있습니다.|
> |16 |RemediationIsSuccess|deviceCustomNumber2|TRUE|Microsoft Defender AV 감지에 사용할 수 있습니다. ArcSight 값은 TRUE이면 1, FALSE이면 0입니다.|
> |17 |WasExecutingWhileDetected|deviceCustomNumber1|FALSE|Microsoft Defender AV 감지에 사용할 수 있습니다. ArcSight 값은 TRUE이면 1, FALSE이면 0입니다.|
> |18 |AlertId|externalId|636210704265059241_673569822|모든 검색에 사용할 수 있는 값입니다.|
> |19|LinkToWDATP|flexString1|`https://securitycenter.windows.com/alert/636210704265059241_673569822`|모든 검색에 사용할 수 있는 값입니다.|
> |20|AlertTime|deviceReceiptTime|2017-05-07T01:56:59.3191352Z|이벤트가 발생한 시간입니다. 모든 검색에 사용할 수 있는 값입니다.|
> | 21|MachineDomain|sourceDnsDomain|contoso.com|AAD에 가입된 디바이스와 관련이 없는 도메인 이름입니다. 모든 검색에 사용할 수 있는 값입니다.|
> |22|배우|deviceCustomString4|BORON|알려진 배우 그룹과 관련된 경고에 사용할 수 있습니다.|
> |21+5|ComputerDnsName|매핑 없음|liz-bean.contoso.com|디바이스의 정식 도메인 이름입니다. 모든 검색에 사용할 수 있는 값입니다.|
> ||LogOnUsers|sourceUserId|contoso\liz-bean; contoso\jay-hardee|이벤트 당시 대화형 로그온 사용자의 도메인 및 사용자입니다. 참고: Windows 10 버전 1607의 디바이스에서는 도메인 정보를 사용할 수 없습니다.|
> ||InternalIPv4List|매핑 없음|192.168.1.7, 10.1.14.1|활성 네트워크 인터페이스에 대한 IPV4 내부 IP 목록입니다.|
> ||InternalIPv6List|매핑 없음|fd30:0000:0000:0001:ff4e:003e:0009:000e, FE80:CD00:0000:0CDE:1257:0000:211E:729C|활성 네트워크 인터페이스에 대한 IPV6 내부 IP 목록입니다.|
> ||LinkToMTP|매핑 없음|`https://securitycenter.windows.com/alert/da637370718981685665_16349121`|모든 검색에 사용할 수 있는 값입니다.
> ||IncidentLinkToMTP|매핑 없음|`"https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM`|모든 검색에 사용할 수 있는 값입니다.
> ||IncidentLinkToWDATP|매핑 없음|`https://securitycenter.windows.com/preferences2/integration/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM`|모든 검색에 사용할 수 있는 값입니다.
> |내부 필드|LastProcessedTimeUtc|매핑 없음|2017-05-07T01:56:58.9936648Z|이벤트가 백엔드에 도착한 시간입니다. 이 필드는 검색된 시간 범위에 대한 요청 매개 변수를 설정할 때 사용할 수 있습니다.|
> ||일부가 아닌 경우|deviceVendor||ArcSight 매핑의 정적 값 - 'Microsoft'.|
> ||일부가 아닌 경우|deviceProduct||ArcSight 매핑의 정적 값 - 'Microsoft Defender ATP'.|
> ||일부가 아닌 경우|deviceVersion||ArcSight 매핑의 정적 값 - '2.0'으로, 매핑 버전을 식별하는 데 사용됩니다.|

:::image type="content" alt-text="번호가 있는 경고 이미지입니다." source="images/atp-alert-page.png" lightbox="images/atp-alert-page.png":::

:::image type="content" alt-text="번호가 있는 경고 세부 정보 창의 이미지입니다." source="images/atp-siem-mapping13.png":::

:::image type="content" alt-text="숫자1이 있는 아티팩트 타임라인의 이미지입니다." source="images/atp-siem-mapping3.png" lightbox="images/atp-siem-mapping3.png":::

:::image type="content" alt-text="숫자 2가 있는 아티팩트 타임라인의 이미지입니다." source="images/atp-siem-mapping4.png" lightbox="images/atp-siem-mapping4.png":::

:::image type="content" alt-text="이미지 컴퓨터 보기." source="images/atp-mapping6.png" lightbox="images/atp-mapping6.png":::

:::image type="content" alt-text="이미지 브라우저 URL입니다." source="images/atp-mapping5.png" lightbox="images/atp-mapping5.png":::

:::image type="content" alt-text="이미지 배우 경고." source="images/atp-mapping7.png" lightbox="images/atp-mapping7.png":::

## <a name="related-topics"></a>관련 항목

- [끝점용 Microsoft Defender에서 SIEM 통합 사용](enable-siem-integration.md)
- [끝점 검색을 위해 Microsoft Defender를 끌어오도록 ArcSight 구성](configure-arcsight.md)
- [REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기](pull-alerts-using-rest-api.md)
- [SIEM 도구 통합 문제 해결](troubleshoot-siem.md)
