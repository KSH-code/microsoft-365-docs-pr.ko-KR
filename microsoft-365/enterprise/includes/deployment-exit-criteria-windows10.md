<a name="crit-windows10-step1"></a>
### <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>필수 작업: Microsoft 365 도메인 추가 및 확인

Office 365 및 Intune 구독을 위한 Azure AD 테넌트는 "onmicrosoft.com"을 포함하는 도메인 이름이 아니라 인터넷 도메인 이름(예: contoso.com)으로 구성됩니다. 

이렇게 하지 않으면 구성할 수 있는 인증 방법이 제한됩니다. 예를 들어, 통과 인증 및 페더레이션 인증에서는 "onmicrosoft.com" 도메인 이름을 사용할 수 없습니다.

필요한 경우 [1단계](../windows10-prepare-your-org.md)를 통해 이 요구 사항을 충족할 수 있습니다.

### <a name="optional-your-users-are-added-and-licensed"></a>선택적 작업: 사용자 추가 및 사용 허가

사용자에 해당하는 계정은 Office 365 및 Intune 구독을 위한 Azure AD 테넌트에 직접 추가되거나 온-프레미스 Active Directory Domain Services(AD DS)에서의 디렉터리 동기화를 통해 추가됩니다.

사용자가 추가되면 전역 또는 사용자 관리자로서 직접, 또는 그룹 구성원 자격을 통해 자동으로 Microsoft 365 Enterprise 라이선스를 할당할 수 있습니다.

필요한 경우 [1단계](../windows10-prepare-your-org.md)를 통해 이 옵션을 충족할 수 있습니다.

### <a name="optional-diagnostics-are-enabled"></a>선택 사항: 진단 사용

그룹 정책, Microsoft Intune, 레지스트리 편집기를 사용한 진단 데이터 설정 또는 명령 프롬프트에서 진단 데이터 설정을 사용합니다.

필요한 경우 [1단계](../windows10-prepare-your-org.md)를 통해 이 옵션을 충족할 수 있습니다.

<a name="crit-windows10-step2"></a>
### <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>현재 위치 업그레이드를 위한 필수 작업: 운영 체제 배포를 위한 Configuration Manager 작업 시퀀스 생성

Windows 7 또는 Windows 8.1이 실행되는 장치에서 현재 위치 업그레이드를 진행하기 위한 Configuration Manager 작업 시퀀스를 시작하려면 다음을 수행해야 합니다.

- 적절한 Windows 진단 데이터 수준 설정
- Windows 업그레이드 준비 상태 확인
- Windows 10 운영 체제 이미지에 장치 컬렉션 및 운영 체제 배포를 포함하는 Configuration Manager 작업 시퀀스 생성

이 작업이 완료되면 Windows를 업그레이드할 준비가 된 장치에서 현재 위치 업그레이드를 수행할 수 있습니다. Microsoft 365 Enterprise를 최대한 활용하기 위해 Windows 7 및 Windows 8.1이 실행되는 장치를 최대한 많이 업그레이드합니다. 

Windows 10 Enterprise를 실행하는 모든 장치는 Microsoft 365 Enterprise의 통합 솔루션 이점을 누릴 수 있습니다. Windows 7 또는 Windows 8.1이 실행되는 나머지 장치는 클라우드 연결 기술 및 Windows 10 Enterprise의 고급 보안 기능을 사용할 수 없습니다.

필요한 경우 [2단계](../windows10-deploy-inplaceupgrade.md)를 통해 이 요구 사항을 충족할 수 있습니다.

<a name="crit-windows10-step3"></a>
### <a name="required-for-new-devices-configured-windows-autopilot"></a>새 장치를 위한 필수 작업: Windows Autopilot 구성

Windows Autopilot을 사용하여 새 장치에 Windows 10 Enterprise를 배포하고 사용자 지정하려면 다음을 수행해야 합니다.

- 적절한 Windows 진단 데이터 수준 구성
- 다음을 포함하는 Windows Autopilot에 대한 필수 구성 요소 구성
   - 장치 등록 및 OOBE 사용자 지정
   - OOBE에 대한 회사 브랜딩
   - Microsoft Intune에서 MDM 자동 등록
   - Windows Autopilot에서 사용되는 클라우드 서비스에 대한 네트워크 연결
- Windows 10, 버전 1703 이상이 미리 설치된 장치
- 조직을 위한 Windows Autopilot Deployment 프로그램 선택

Windows Autopilot 구성이 완료되면 다음에 대한 OOBE(첫 실행 경험)을 위해 Windows 10 Enterprise를 구성하고 사용자 지정하는 데 사용할 수 있습니다.

- 새 장치
- 조직에서 기본 설치가 이미 완료된 장치 

Windows Autopilot은 해당 장치를 구성하고 Azure AD에 연결합니다.

Windows Autopilot이 없으면 Azure AD 연결하는 작업을 비롯하여 새 장치를 수동으로 구성해야 합니다.

필요한 경우 [3단계](../windows10-deploy-autopilot.md)를 통해 이 요구 사항을 충족할 수 있습니다.

<a name="crit-windows10-step4"></a>
### <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>선택적 작업: Windows Analytics 장치 상태를 사용하여 Windows 10 Enterprise 기반 장치 모니터링

“장치 상태 기능을 통해 장치의 상태 모니터링”의 정보를 사용하여 최종 사용자에게 영향을 주는 문제 감지 및 수정. 최종 사용자 문제를 빠르게 처리하면 지원 비용이 절감되고, Windows 10 Enterprise 채택에 대한 IT 부서 노력을 보여 줌으로써 조직 전체의 채택에 도움이 될 수 있습니다. 

필요한 경우 [4단계](../windows10-enable-windows-analytics.md)를 통해 이 옵션을 충족할 수 있습니다.

<a name="crit-windows10-step5a"></a>
### <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>필수 작업: Windows Defender 바이러스 백신 또는 맬웨어 방지 솔루션 사용

Windows Defender 바이러스 백신 또는 자신의 바이러스 백신 솔루션을 배포하여 Windows 10 Enterprise 실행 장치를 악성 소프트웨어로부터 보호. Windows Defender 바이러스 백신를 배포한 경우, 바이러스 백신 이벤트 및 활동을 모니터링하기 위한 System Center Configuration Manager 또는 Microsoft Intune과 같은 보고 방법이 구현된 것입니다.

필요한 경우 [5단계](../windows10-enable-security-features.md#windows10-sec-av)를 통해 이 요구 사항을 충족할 수 있습니다.

<a name="crit-windows10-step5b"></a>
### <a name="required-you-are-using-windows-defender-exploit-guard"></a>필수 작업: Windows Defender Exploit Guard 사용

Windows Defender Exploit Guard를 배포하여 Windows 10 Enterprise 실행 장치를 침입으로부터 보호하고 침입 이벤트 및 활동을 모니터링하기 위한 System Center Configuration Manager 또는 Microsoft Intune과 같은 보고 방법 구현

필요한 경우 [5단계](../windows10-enable-security-features.md#windows10-sec-eg)를 통해 이 요구 사항을 충족할 수 있습니다.

<a name="crit-windows10-step5c"></a>
### <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a>필수 작업: Microsoft Defender Advanced Threat Protection 사용(Microsoft 365 Enterprise E5만 해당)

Microsoft Defender ATP(Advanced Threat Protection)를 배포하여 네트워크 및 Windows 10 Enterprise 실행 장치에 대한 고급 위협 감지, 조사, 대응 

필요에 따라 다른 도구에 Microsoft Defender ATP를 통합하여 기능 확장

필요한 경우 [5단계](../windows10-enable-security-features.md#windows10-sec-atp)를 통해 이 요구 사항을 충족할 수 있습니다.
