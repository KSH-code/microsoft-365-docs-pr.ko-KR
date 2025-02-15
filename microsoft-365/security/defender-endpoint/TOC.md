# [엔드포인트용 Microsoft Defender](index.yml) 

## [개요]()
### [엔드포인트용 Microsoft Defender란 무엇인가요?](microsoft-defender-endpoint.md)
### [엔드포인트용 Defender 플랜 1과 플랜 2 비교](defender-endpoint-plan-1-2.md)
### [최소 요구 사항](minimum-requirements.md)
### [엔드포인트용 Microsoft Defender의 새로운 기능](whats-new-in-microsoft-defender-atp.md)
### [미리 보기 기능](preview.md)
### [데이터 저장 및 개인 정보](data-storage-privacy.md)
### [Microsoft Defender 보안 센터 개요](use.md)
### [포털 개요](portal-overview.md)
### [엔드포인드용 Defender 플랜 1(미리 보기)]()
#### [개요](defender-endpoint-plan-1.md)
#### [설정 및 구성](mde-p1-setup-configuration.md)
#### [시작](mde-plan1-getting-started.md)
#### [유지 관리 및 운영](mde-p1-maintenance-operations.md)
### [엔드포인트용 Microsoft Defender(미국 정부 고객용)](gov.md)
### [Microsoft Defender for Endpoint(Windows가 아닌 플랫폼)](non-windows.md)


## [기능 평가](evaluation-lab.md)

## [배포 계획](deployment-strategy.md)

## [배포 가이드]()
### [배포 단계](deployment-phases.md)
### [1 단계: 준비](prepare-deployment.md)
### [2 단계: 설정](production-deployment.md)
### [3 단계: 온보딩]()
#### [온보딩 개요](onboarding.md)
#### [배포 링](deployment-rings.md)
#### [Microsoft Endpoint Configuration Manager를 사용하여 온보딩](onboarding-endpoint-configuration-manager.md)
#### [Microsoft Endpoint Manager를 사용하여 온보딩](onboarding-endpoint-manager.md)

## [마이그레이션 가이드](migration-guides.md)
### [타사 엔드포인트 보호에서 끝점용 Defender로 전환](switch-to-microsoft-defender-migration.md)
#### [1 단계: 준비](switch-to-microsoft-defender-prepare.md)
#### [2 단계: 설정](switch-to-microsoft-defender-setup.md)
#### [3 단계: 온보딩](switch-to-microsoft-defender-onboard.md)



### [마이그레이션 후 엔드포인트용 Defender 관리](manage-atp-post-migration.md)
#### [Intune 사용(권장)](manage-atp-post-migration-intune.md)
#### [Configuration Manager 사용](manage-atp-post-migration-configuration-manager.md)
#### [그룹 정책 사용](manage-atp-post-migration-group-policy-objects.md)
#### [PowerShell, WMI 또는 MPCmdRun.exe 사용](manage-atp-post-migration-other-tools.md)
#### [서버 마이그레이션 시나리오](server-migration.md)

## [장치 구성 및 온보드]()
### [디바이스 온보딩 및 Endpoint용 Microsoft Defender 기능 구성](onboard-configure.md)


### [Windows 및 Windows Server의 엔드포인트용 Microsoft Defender]()
#### [Windows 엔드포인트용 온보딩 도구 및 방법](configure-endpoints.md)
#### [Windows 장치 및 Windows 서버 온보딩]()

##### [이전 버전의 Windows 온보딩](onboard-downlevel.md)


##### [Windows 장치 및 Windows 서버 온보딩]()
###### [Windows Server 2012 R2, 2016, 반기 채널, 2019 및 2022 온보딩](configure-server-endpoints.md)
###### [로컬 스크립트를 사용하여 Windows 장치 온보딩](configure-endpoints-script.md)
###### [그룹 정책을 사용하여 Windows 장치 온보딩](configure-endpoints-gp.md)
###### [Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩](configure-endpoints-sccm.md)
###### [모바일 장치 관리 도구를 사용한 Windows 장치 온보딩](configure-endpoints-mdm.md)
###### [비영구 VDI(가상 데스크톱 인프라) 장치 온보딩](configure-endpoints-vdi.md)
###### [Windows Virtual Desktop에서 Windows 10 다중 세션 장치 온보딩](onboard-windows-multi-session-device.md)




#### [Azure Defender와 통합](azure-server-integration.md)

#### [인터넷 액세스 없이 장치 온보딩](onboard-offline-machines.md)
#### [새로 온보딩된 장치에서 검색 테스트 실행](run-detection-test.md)
#### [장치에서 시뮬레이션된 공격 실행](attack-simulations.md)
#### [프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md)
#### [온보딩 또는 오프보딩 알림 규칙 만들기](onboarding-notification.md)

#### [응용 프로그램 사용 조건](mde-terms-windows.md)


### [다른 운영 체제의 엔드포인트용 Microsoft Defender]()
#### [Windows가 아닌 장치 온보딩](configure-endpoints-non-windows.md)

#### [Microsoft Defender for Endpoint(macOS용)]()
##### [macOS의 Microsoft Defender for Endpoint 개요](microsoft-defender-endpoint-mac.md)
##### [새로운 기능](mac-whatsnew.md)

##### [배포]()
###### [Microsoft Intune 기반 배포](mac-install-with-intune.md)
###### [JAMF Pro 기반 배포]()
####### [Jamf Pro를 사용하여 Microsoft Defender for Endpoint(macOS용) 배포](mac-install-with-jamf.md)
####### [Jamf Pro에 로그인](mac-install-jamfpro-login.md)
####### [장치 그룹 설정](mac-jamfpro-device-groups.md)
####### [정책 설정](mac-jamfpro-policies.md)
####### [장치 등록](mac-jamfpro-enroll-devices.md)

###### [다른 MDM(모바일 장치 관리) 시스템을 사용하여 배포](mac-install-with-other-mdm.md)
###### [수동 배포](mac-install-manually.md)
##### [업데이트](mac-updates.md)

##### [구성]()
###### [제외 구성 및 유효성 검사](mac-exclusions.md)
###### [기본 설정](mac-preferences.md)
###### [잠재적으로 원하지 않는 응용 프로그램 검색 및 차단](mac-pua.md)
###### [장치 제어]()
####### [장치 제어 개요](mac-device-control-overview.md)
####### [JAMF 예제](mac-device-control-jamf.md)
####### [Intune 예제](mac-device-control-intune.md)
###### [검색 예약](mac-schedule-scan.md)

##### [문제 해결]()
###### [설치 문제 해결](mac-support-install.md)
###### [성능 문제 해결](mac-support-perf.md)
###### [클라우드 연결 문제 해결](troubleshoot-cloud-connect-mdemac.md)
###### [커널 확장 문제 해결](mac-support-kext.md)
###### [라이선스 문제 해결](mac-support-license.md)

##### [개인 정보](mac-privacy.md)
##### [리소스](mac-resources.md)
##### [응용 프로그램 사용 조건](mde-terms-mac.md)

#### [Microsoft Defender for Endpoint(Linux용)]()
##### [Microsoft Defender for Endpoint(iOS용) 개요](microsoft-defender-endpoint-linux.md)
##### [새로운 기능](linux-whatsnew.md)
##### [배포]()
###### [수동 배포](linux-install-manually.md)
###### [Puppet 기반 배포](linux-install-with-puppet.md)
###### [Ansible 기반 배포](linux-install-with-ansible.md)
###### [Chef를 통해 Microsoft Defender for Endpoint(Linux용) 배포](linux-deploy-defender-for-endpoint-with-chef.md)

##### [업데이트](linux-updates.md)

##### [구성]()
###### [제외 구성 및 유효성 검사](linux-exclusions.md)
###### [정적 프록시 구성](linux-static-proxy-configuration.md)
###### [기본 설정](linux-preferences.md)
###### [잠재적으로 원하지 않는 응용 프로그램 검색 및 차단](linux-pua.md)
###### [Microsoft Defender for Endpoint(Linux용) 검사 예약](linux-schedule-scan-atp.md)
###### [엔드포인트용 Microsoft Defender(Linux) 업데이트 예약](linux-update-MDE-Linux.md)


##### [문제 해결]()
###### [설치 문제 해결](linux-support-install.md)
###### [에이전트 상태 문제 조사](health-status.md)
###### [클라우드 연결 문제 해결](linux-support-connectivity.md)
###### [RHEL 6 설치 문제 해결](linux-support-rhel.md)
###### [성능 문제 해결](linux-support-perf.md)
###### [누락된 이벤트 문제 해결](linux-support-events.md)

##### [개인 정보](linux-privacy.md)
##### [리소스](linux-resources.md)

#### [Mobile Threat Defense]()
##### [모바일 위협 방어 개요](mtd.md)

##### [Microsoft Defender for Endpoint(Android용)]()
###### [Microsoft Defender for Endpoint(iOS용) 개요](microsoft-defender-endpoint-android.md)
###### [새로운 기능](android-whatsnew.md)

###### [배포]()
####### [Microsoft Intune으로 Microsoft Defender for Endpoint(Android용) 배포](android-intune.md)

###### [구성]()
####### [Microsoft Defender for Endpoint(Android용) 기능 구성](android-configure.md)
####### [앱 보호 정책을 사용하여 엔드포인트용 Microsoft Defender 위험 신호 구성](android-configure-mam.md)

###### [개인 정보]()
####### [Microsoft Defender for Endpoint(Android용) - 개인 정보](android-privacy.md)

###### [문제 해결]()
####### [문제 해결](android-support-signin.md)

##### [Microsoft Defender for Endpoint(iOS용)]()
###### [Microsoft Defender for Endpoint(iOS용) 개요](microsoft-defender-endpoint-ios.md)
###### [새로운 기능](ios-whatsnew.md)

###### [배포]()
####### [Intune을 통해 Microsoft Defender for Endpoint(iOS용) 배포](ios-install.md)
####### [등록되지 않은 장치를 통해 Microsoft 엔드포인트용 Microsoft Defender(iOS용) 배포](ios-install-unmanaged.md)

###### [iOS 기능 구성](ios-configure-features.md)

###### [FAQ 및 문제 해결](ios-troubleshoot.md)

###### [개인 정보](ios-privacy.md)

##### [엔드포인트용 Microsoft Defender 응용 프로그램 사용 조건](mde-terms-mobile.md) 

### [Microsoft Endpoint Manager를 사용하여 장치에서 엔드포인트용 Microsoft Defender 구성 설정 관리](security-config-management.md)

### [온보딩 문제 해결]()
#### [온보딩 중 문제 해결](troubleshoot-onboarding.md)
#### [구독 및 포털 액세스 문제 해결](troubleshoot-onboarding-error-messages.md)
#### [보안 구성 관리 온보딩 문제 해결](troubleshoot-security-config-mgt.md)





### [포털 설정 구성]()
#### [기본 설정](preferences-setup.md)
#### [일반]()
##### [데이터 저장소 위치 확인 및 데이터 보존 설정 업데이트](data-retention-settings.md)
##### [경고 알림 구성](configure-email-notifications.md)
##### [취약성 전자 메일 알림 구성](configure-vulnerability-email-notifications.md)
##### [고급 기능 구성](advanced-features.md)

#### [사용 권한]()
##### [기본 권한을 사용하여 포털에 액세스](basic-permissions.md)
##### [RBAC를 사용하여 포털 액세스 관리](rbac.md)
###### [역할 만들기 및 관리](user-roles.md)
###### [장치 그룹 만들기 및 관리](machine-groups.md)
###### [장치 태그 만들기 및 관리](machine-tags.md)

#### [규칙]()
##### [제거 규칙 관리](manage-suppression-rules.md)
##### [지표 만들기](manage-indicators.md)
###### [파일에 대한 지표 만들기](indicator-file.md)
###### [IP 및 URL/도메인에 대한 지표 만들기](indicator-ip-domain.md)
###### [인증서에 대한 지표 만들기](indicator-certificates.md)
###### [지표 관리](indicator-manage.md)
##### [자동화 파일 업로드 관리](manage-automation-file-uploads.md)
##### [자동화 폴더 제외 관리](manage-automation-folder-exclusions.md)

#### [장치 관리]()
##### [온보딩 장치](onboard-configure.md)
##### [오프보딩 장치](offboard-machines.md)
##### [장치가 올바르게 구성되어 있는지 확인](configure-machines.md)
##### [장치 온보딩 모니터링 및 늘리기](configure-machines-onboarding.md)

#### [Microsoft Defender 보안 센터 표준 시간대 설정 구성](time-settings.md)

## [위협 탐지 및 끝점 보호]()
### [위협 및 취약성 관리]()
#### [개요](next-gen-threat-and-vuln-mgt.md)
#### [시작]()
##### [권한 및 필수 구성 요소](tvm-prerequisites.md)
##### [지원되는 운영 체제 플랫폼 및 기능](tvm-supported-os.md)
##### [장치 값 할당](tvm-assign-device-value.md)
#### [보안 상태 평가]()
##### [대시보드 인사이트](tvm-dashboard-insights.md)
##### [노출 점수](tvm-exposure-score.md)
##### [장치용 Microsoft Secure Score](tvm-microsoft-secure-score-devices.md)
#### [보안 자세 개선 및 위험 감소]()
##### [보안 권장 사항 해결](tvm-security-recommendation.md)
##### [취약성 수정](tvm-remediation.md)
##### [보안 권장 사항에 대한 예외](tvm-exception.md)
##### [지원 종료 소프트웨어 계획](tvm-end-of-support-software.md)
##### [제로 데이 취약성 완화](tvm-zero-day-vulnerabilities.md)
#### [장치의 취약성 이해]()
##### [소프트웨어 인벤토리](tvm-software-inventory.md)
##### [내 조직의 취약성](tvm-weaknesses.md)
##### [이벤트 타임라인](threat-and-vuln-mgt-event-timeline.md)
##### [취약한 장치 보고서](tvm-vulnerable-devices-report.md)
##### [노출된 장치 헌팅](tvm-hunt-exposed-devices.md)

### [장치 검색]()
#### [장치 검색 개요](device-discovery.md)
#### [장치 검색 구성](configure-device-discovery.md)
#### [장치 검색 FAQ](device-discovery-faq.md)

### [네트워크 장치](network-devices.md)

### [엔드포인트용 Microsoft Defender 호스트 방화벽 보고](host-firewall-reporting.md)

### [공격 표면 감소]()
#### [공격 표면 감소 개요](overview-attack-surface-reduction.md)
#### [공격 표면 감소 기능 구성](configure-attack-surface-reduction.md)
#### [공격 표면 감소 규칙에 대한 자세한 정보](attack-surface-reduction.md)
#### [공격 표면 감소 규칙](attack-surface-reduction-rules.md)
#### [공격 표면 감소 규칙 배포](attack-surface-reduction-rules-deployment.md)
#### [공격 표면 감소 규칙 평가](evaluate-attack-surface-reduction.md)
#### [공격 표면 감소 규칙 사용](enable-attack-surface-reduction.md)
#### [공격 표면 감소 규칙 사용자 지정](customize-attack-surface-reduction.md)
#### [공격 표면 감소 FAQ](attack-surface-reduction-faq.yml)
#### [공격 표면 감소 이벤트 보기](event-views.md)
#### [공격 노출 영역 감소에 감사 모드 사용](audit-windows-defender.md)

### 차세대 보호
#### [차세대 보호 개요](next-generation-protection.md)
##### [Microsoft Defender 바이러스 백신 개요](microsoft-defender-antivirus-windows.md)
##### [Windows Server의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
##### [함께 활용: Microsoft Defender 바이러스 백신 및 Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)
##### [함께 활용: Microsoft Defender 바이러스 백신 및 Office 365](office-365-microsoft-defender-antivirus.md)
#### [Microsoft Defender 바이러스 백신 평가](evaluate-microsoft-defender-antivirus.md)
#### [Microsoft Defender 바이러스 백신 기능 구성](configure-microsoft-defender-antivirus-features.md)
#### [클라우드 보호 및 Microsoft Defender 바이러스 백신](cloud-protection-microsoft-defender-antivirus.md)
##### [클라우드 보호를 사용해야 하는 이유](why-cloud-protection-should-be-on-mdav.md)
##### [클라우드 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md)
##### [클라우드 보호 수준 지정](specify-cloud-protection-level-microsoft-defender-antivirus.md)
##### [클라우드 보호 및 샘플 제출](cloud-protection-microsoft-antivirus-sample-submission.md)
#### [Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사](configure-network-connections-microsoft-defender-antivirus.md)
#### [무단 보호를 사용하여 보안 설정 보호](prevent-changes-to-security-settings-with-tamper-protection.md)
#### [즉각적 차단 켜기](configure-block-at-first-sight-microsoft-defender-antivirus.md)
#### [클라우드 차단 제한 시간 구성](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
#### [동작, 추론 및 실시간 보호 구성](configure-protection-features-microsoft-defender-antivirus.md)
#### [잠재적으로 원하지 않는 응용 프로그램 검색 및 차단](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
#### [그룹 정책에서 Microsoft Defender 바이러스 백신 항상 보호 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md)
#### [Microsoft Defender 바이러스 백신 검색에 대한 수정 구성](configure-remediation-microsoft-defender-antivirus.md)
#### [Microsoft Defender 바이러스 백신 검사 구성](schedule-antivirus-scans.md)
##### [그룹 정책을 사용하여 검사 예약](schedule-antivirus-scans-group-policy.md)
##### [PowerShell을 사용하여 검사 예약](schedule-antivirus-scans-powershell.md)
##### [WMI를 사용하여 검사 예약](schedule-antivirus-scans-wmi.md)
#### [Microsoft Defender 바이러스 백신에서 제한된 주기적 검사 사용](limited-periodic-scanning-microsoft-defender-antivirus.md)
#### [Microsoft Defender 바이러스 백신 성능 조정](tune-performance-defender-antivirus.md)
#### [다른 보안 제품과의 호환성](microsoft-defender-antivirus-compatibility.md)

#### [바이러스 백신 및 맬웨어 방지 업데이트 다운로드](manage-updates-baselines-microsoft-defender-antivirus.md)
##### [Microsoft Defender 바이러스 백신 보호 업데이트의 출처 관리](manage-protection-updates-microsoft-defender-antivirus.md)
##### [보호 업데이트를 다운로드하여 적용해야 하는 경우에 대한 예약 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md)
##### [Microsoft Defender 업데이트를 위한 점차적인 롤아웃 절차 관리](manage-gradual-rollout.md)
##### [Microsoft Defender 업데이트를 위한 점차적인 롤아웃 절차 구성](configure-updates.md)
##### [Microsoft Defender 바이러스 백신 업데이트 및 만료된 엔드포인트에 대한 검사 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md)
##### [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md)
##### [모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)

#### [조직에 대해 Microsoft Defender 바이러스 백신 관리](configuration-management-reference-microsoft-defender-antivirus.md)
##### [Microsoft Endpoint Manager를 사용하여 Microsoft Defender 바이러스 백신 관리](use-intune-config-manager-microsoft-defender-antivirus.md)
##### [그룹 정책 설정을 사용하여 Microsoft Defender 바이러스 백신 관리](use-group-policy-microsoft-defender-antivirus.md)
##### [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리](use-powershell-cmdlets-microsoft-defender-antivirus.md)
##### [WMI(Windows Management Instrumentation)를 사용하여 Microsoft Defender 바이러스 백신 관리](use-wmi-microsoft-defender-antivirus.md)
##### [mpcmdrun.exe 도구를 사용하여 Microsoft Defender 바이러스 백신 관리](command-line-arguments-microsoft-defender-antivirus.md)
##### [엔드포인트에 표시되는 알림 구성](configure-notifications-microsoft-defender-antivirus.md)
##### [사용자가 로컬에서 Microsoft Defender 바이러스 백신 정책 설정을 수정할 수 있게 할지 지정](configure-local-policy-overrides-microsoft-defender-antivirus.md)
##### [사용자가 Microsoft Defender 바이러스 백신 사용자 인터페이스를 보고 이와 상호 작용할 수 있게 할지 지정](prevent-end-user-interaction-microsoft-defender-antivirus.md)

#### [Microsoft Defender 바이러스 백신 배포 및 보고](deploy-manage-report-microsoft-defender-antivirus.md)
##### [Microsoft Defender 바이러스 백신 배포 및 사용](deploy-microsoft-defender-antivirus.md)
##### [VDI(가상 데스크톱 인프라) 환경에서 Microsoft Defender 바이러스 백신의 배포 가이드](deployment-vdi-microsoft-defender-antivirus.md)
##### [Microsoft Defender 바이러스 백신에 대한 보고](report-monitor-microsoft-defender-antivirus.md)

#### [검사 및 수정](review-scan-results-microsoft-defender-antivirus.md)
##### [요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행](run-scan-microsoft-defender-antivirus.md)
##### [Microsoft Defender 오프라인 검사의 결과 실행 및 검토](microsoft-defender-offline.md)
##### [Microsoft Defender 바이러스 백신 검사 옵션 구성](configure-advanced-scan-types-microsoft-defender-antivirus.md)
##### [Microsoft Defender 바이러스 백신에서 격리된 파일 복원](restore-quarantined-files-microsoft-defender-antivirus.md)

#### [Microsoft Defender 바이러스 백신 제외](configure-exclusions-microsoft-defender-antivirus.md)
##### [파일 확장명 및 폴더 위치에 기반하여 제외](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
##### [프로세스에서 연 파일에 대한 제외](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
##### [Windows Server에 대한 제외](configure-server-exclusions-microsoft-defender-antivirus.md)
##### [피해야 하는 일반적인 실수](common-exclusion-mistakes-microsoft-defender-antivirus.md)

#### Windows Defender 바이러스 백신 문제 해결
##### [업데이트 규정 준수에서 Microsoft Defender 바이러스 백신 보고 문제 해결](troubleshoot-reporting.md)
##### [성능 문제 해결](troubleshoot-performance-issues.md)
##### [이벤트 로그 및 오류 코드를 검토하여 Microsoft Defender 바이러스 백신 문제 해결](troubleshoot-microsoft-defender-antivirus.md)
##### [타사 솔루션에서 마이그레이션하는 동안 Microsoft Defender 바이러스 백신 문제 해결](troubleshoot-microsoft-defender-antivirus-when-migrating.md)

#### [악용 방지]()
##### [악용으로부터 장치 보호](exploit-protection.md)
##### [악용 방지 평가](evaluate-exploit-protection.md)
##### [악용 방지 사용](enable-exploit-protection.md)
##### [악용 방지 사용자 지정](customize-exploit-protection.md)
##### [악용 보호 구성 가져오기, 내보내기 및 배포하기](import-export-exploit-protection-emet-xml.md)
##### [악용 방지 참고자료](exploit-protection-reference.md)

#### [네트워크 보호]()
##### [네트워크 보호](network-protection.md)
##### [네트워크 보호 평가](evaluate-network-protection.md)
##### [네트워크 보호 설정 켜기](enable-network-protection.md)

#### [웹 보호]()
##### [웹 보호 개요](web-protection-overview.md)
##### [웹 위협 방지]()
###### [웹 위협 방지 개요](web-threat-protection.md)
###### [웹 보안 모니터링](web-protection-monitoring.md)
###### [웹 위협에 대응](web-protection-response.md)
##### [웹 컨텐츠 필터링](web-content-filtering.md)

#### [제어된 폴더 액세스]()
##### [폴더 보호](controlled-folders.md)
##### [제어된 폴더 액세스 평가](evaluate-controlled-folder-access.md)
##### [제어된 폴더 액세스 사용](enable-controlled-folders.md)
##### [제어된 폴더 액세스 사용자 지정](customize-controlled-folders.md)

#### [장치 제어]()
##### [이동식 저장소 보호](device-control-removable-storage-protection.md)
##### [이동식 저장소 액세스 제어](device-control-removable-storage-access-control.md)
##### [디바이스 설치](mde-device-control-device-installation.md)
##### [장치 제어 프린터 보호](printer-protection.md)
##### [장치 제어 보고서](device-control-report.md)

#### [동작 차단 및 제약]()
##### [동작 차단 및 제약](behavioral-blocking-containment.md)
##### [클라이언트 동작 차단](client-behavioral-blocking.md)
##### [피드백-루프 차단](feedback-loop-blocking.md)


### [Endpoint용 Microsoft Defender에서 가양성/가음성 처리](defender-endpoint-false-positives-negatives.md)


### [장치 구성 관리]()

#### [보안 기준에 대한 규정 준수 강화](configure-machines-security-baseline.md)
#### [공격 표면 감소 규칙 및 검색 최적화](configure-machines-asr.md)

## [위협 탐지 및 응답]()
### [엔드포인트 검색 및 대응]()
#### [엔드포인트 검색 및 대응 개요](overview-endpoint-detection-response.md)
#### [보안 운영 대시보드](security-operations-dashboard.md)
#### [인시던트 큐]()
##### [인시던트 큐 보기 및 구성](view-incidents-queue.md)
##### [인시던트 관리](manage-incidents.md)
##### [인시던트 조사](investigate-incidents.md)

#### [경고 큐]()
##### [Microsoft 365 Defender의 경고 큐](alerts-queue-endpoint-detection-response.md)
##### [경고 큐 보기 및 구성](alerts-queue.md)
##### [경고 검토](review-alerts.md)
##### [경고 관리](manage-alerts.md)
##### [경고 조사](investigate-alerts.md)
##### [파일 조사](investigate-files.md)
##### [장치 조사](investigate-machines.md)
##### [IP 주소 조사](investigate-ip.md)
##### [도메인 조사](investigate-domain.md)
###### [전달 프록시 뒤에 발생하는 연결 이벤트 조사](investigate-behind-proxy.md)
##### [사용자 계정 조사](investigate-user.md)

#### [장치 목록]()
##### [장치 목록 보기 및 구성](machines-view-overview.md)
##### [장치 타임라인 이벤트 플래그](device-timeline-event-flag.md)
##### [장치 그룹 및 태그 관리](machine-tags.md)

#### [대응 조치 실행]()
##### [장치에 대해 대응 조치 실행]()
###### [장치에 대한 대응 조치](respond-machine-alerts.md)
###### [태그 관리](respond-machine-alerts.md#manage-tags)
###### [자동화된 조사 시작](respond-machine-alerts.md#initiate-automated-investigation)
###### [실시간 대응 세션 시작](respond-machine-alerts.md#initiate-live-response-session)
###### [조사 패키지 수집](respond-machine-alerts.md#collect-investigation-package-from-devices)
###### [바이러스 백신 검사 실행](respond-machine-alerts.md#run-microsoft-defender-antivirus-scan-on-devices)
###### [앱 실행 제한](respond-machine-alerts.md#restrict-app-execution)
###### [네트워크에서 장치 격리](respond-machine-alerts.md#isolate-devices-from-the-network)
###### [위협 전문가에게 문의](respond-machine-alerts.md#consult-a-threat-expert)
###### [알림 센터에서 활동 세부 정보 확인](respond-machine-alerts.md#check-activity-details-in-action-center)

##### [파일에 대해 대응 조치 실행]()
###### [파일에 대한 대응 조치](respond-file-alerts.md)
###### [네트워크에서 파일 중지 및 격리](respond-file-alerts.md#stop-and-quarantine-files-in-your-network)
###### [격리로부터 파일 복원](respond-file-alerts.md#restore-file-from-quarantine)
###### [파일을 차단하거나 허용하는 지표 추가](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
###### [위협 전문가에게 문의](respond-file-alerts.md#consult-a-threat-expert)
###### [알림 센터에서 활동 세부 정보 확인](respond-file-alerts.md#check-activity-details-in-action-center)
###### [파일 다운로드 또는 수집](respond-file-alerts.md#download-or-collect-file)
###### [심층 분석](respond-file-alerts.md#deep-analysis)

#### [수정 조치 보기 및 승인](manage-auto-investigation.md)
##### [자동화된 조사의 세부 정보 및 결과 보기](auto-investigation-action-center.md)

#### [실시간 대응을 사용하여 엔터티 조사]()
##### [장치에서 엔터티 조사](live-response.md)
##### [실시간 대응 명령 예제](live-response-command-examples.md)

#### [민감도 레이블을 사용하여 인시던트 대응의 우선 순위 지정](information-protection-investigation.md)

#### [보고]()
##### [Power BI - API를 사용하는 방법 - 샘플](api-power-bi.md)
##### [위협 방지 보고서](threat-protection-reports.md)
#### [컴퓨터 상태 및 규정 준수 보고서](machine-reports.md)

### [지능형 헌팅]()
#### [지능형 헌팅 개요](advanced-hunting-overview.md)
#### [스키마에 대한 이해](advanced-hunting-schema-reference.md)
#### [DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)

### [위협 분석 개요](threat-analytics.md)
#### [분석 보고서 읽기](threat-analytics-analyst-reports.md)

### [차단 모드의 EDR](edr-in-block-mode.md)

### [자동화된 조사 및 대응(AIR)]()
#### [AIR 개요](automated-investigations.md)
#### [AIR의 자동화 수준](automation-levels.md)
#### [AIR 기능 구성](configure-automated-investigations-remediation.md)

### [Microsoft 위협 전문가]()
#### [Microsoft 위협 전문가 개요](microsoft-threat-experts.md)
#### [Microsoft 위협 전문가 기능 구성 및 관리](configure-microsoft-threat-experts.md)



## 참조
### [위협 인텔리전스 개념 이해](threat-indicator-concepts.md)
### [다른 Microsoft 솔루션과 통합 구성]()
#### [조건부 액세스 구성](configure-conditional-access.md)
#### [Microsoft Cloud App Security 통합 구성](microsoft-cloud-app-security-config.md)
### [관리 및 API]()
#### [관리 및 API 개요](management-apis.md)
#### [API 릴리스 정보](api-release-notes.md)
#### [엔드포인트용 Microsoft Defender API]() 
##### [시작]()
###### [엔드포인트용 Microsoft Defender API 라이선스 및 사용 약관](api-terms-of-use.md)
###### [엔드포인트용 Microsoft Defender API에 액세스](apis-intro.md) 
###### [Hello World](api-hello-world.md)
###### [응용 프로그램 컨텍스트를 사용하여 액세스](exposed-apis-create-app-webapp.md)
###### [사용자 컨텍스트를 사용하여 액세스](exposed-apis-create-app-nativeapp.md)



##### [엔드포인트용 Microsoft Defender API 스키마]() 
###### [지원되는 엔드포인트용 Microsoft Defender API](exposed-apis-list.md) 
###### [일반적인 REST API 오류 코드](common-errors.md)
###### [지능형 헌팅](run-advanced-query-api.md)

###### [경고]()
####### [경고 방법 및 속성](alerts.md)
####### [경고 목록](get-alerts.md)
####### [경고 만들기](create-alert-by-reference.md)
####### [일괄 업데이트 경고](batch-update-alerts.md)
####### [경고 업데이트](update-alert.md)
####### [ID별 경고 정보 가져오기](get-alert-info-by-id.md)
####### [경고 관련 도메인 정보 가져오기](get-alert-related-domain-info.md)
####### [경고 관련 파일 정보 가져오기](get-alert-related-files-info.md)
####### [경고 관련 IP 정보 가져오기](get-alert-related-ip-info.md)
####### [경고 관련 장치 정보 가져오기](get-alert-related-machine-info.md)
####### [경고 관련 사용자 정보 가져오기](get-alert-related-user-info.md)


###### [취약성 및 보안 구성 평가]()
####### [평가 방법 및 속성 내보내기](get-assessment-methods-properties.md)
####### [보안 구성 평가 내보내기](get-assessment-secure-config.md)
####### [소프트웨어 인벤토리 재고 내보내기](get-assessment-software-inventory.md)
####### [소프트웨어 취약점 평가 내보내기](get-assessment-software-vulnerabilities.md)

###### [자동화된 조사]()
####### [조사 방법 및 속성](investigation.md)
####### [조사 목록](get-investigation-collection.md)
####### [조사 받기](get-investigation-object.md)
####### [조사 시작](initiate-autoir-investigation.md)

###### [도메인]()
####### [도메인 관련 경고 가져오기](get-domain-related-alerts.md)
####### [도메인 관련 컴퓨터 가져오기](get-domain-related-machines.md)
####### [도메인 통계 가져오기](get-domain-statistics.md)

###### [파일]()
####### [파일 방법 및 속성](files.md)
####### [파일 정보 가져오기](get-file-information.md)
####### [파일 관련 경고 가져오기](get-file-related-alerts.md)
####### [파일 관련 컴퓨터 가져오기](get-file-related-machines.md)
####### [파일 통계 가져오기](get-file-statistics.md)

###### [지표]()
####### [지표 방법 및 속성](ti-indicator.md)
####### [지표 목록](get-ti-indicators-collection.md)
####### [지표 제출](post-ti-indicator.md)
####### [표시기 가져오기](import-ti-indicators.md)
####### [지표 삭제](delete-ti-indicator-by-id.md)

###### [IP]()
####### [IP 관련 경고 가져오기](get-ip-related-alerts.md)
####### [IP 통계 가져오기](get-ip-statistics.md)


###### [컴퓨터]()
####### [컴퓨터 방법 및 속성](machine.md)
####### [컴퓨터 목록](get-machines.md)
####### [ID별 컴퓨터 가져오기](get-machine-by-id.md)
####### [컴퓨터 로그인 사용자 가져오기](get-machine-log-on-users.md)
####### [컴퓨터 관련 경고 가져오기](get-machine-related-alerts.md)
####### [설치된 소프트웨어 가져오기](get-installed-software.md)
####### [발견된 취약성 가져오기](get-discovered-vulnerabilities.md)
####### [보안 권장 사항 가져오기](get-security-recommendations.md)
####### [컴퓨터 태그 추가 또는 제거](add-or-remove-machine-tags.md)
####### [IP별 컴퓨터 찾기](find-machines-by-ip.md)
####### [태그별 컴퓨터 찾기](find-machines-by-tag.md)
####### [누락된 KB 가져오기](get-missing-kbs-machine.md)
####### [장치 값 설정](set-device-value.md)
####### [컴퓨터 업데이트](update-machine-method.md)



###### [컴퓨터 작업]()
####### [컴퓨터 작업 방법 및 속성](machineaction.md)
####### [컴퓨터 작업 목록](get-machineactions-collection.md)
####### [컴퓨터 작업 가져오기](get-machineaction-object.md)
####### [조사 패키지 수집](collect-investigation-package.md)
####### [조사 패키지 SAS URI 가져오기](get-package-sas-uri.md)
####### [라이브 응답 결과 가져오기](get-live-response-result.md)
####### [컴퓨터 격리](isolate-machine.md)
####### [컴퓨터 격리 해제](unisolate-machine.md)
####### [앱 실행 제한](restrict-code-execution.md)
####### [앱 제한 제거](unrestrict-code-execution.md)
####### [바이러스 백신 검사 실행](run-av-scan.md)
####### [실시간 응답 실행](run-live-response.md)
####### [컴퓨터 오프보딩](offboard-machine-api.md)
####### [파일을 중지하고 격리](stop-and-quarantine-file.md)
####### [컴퓨터 작업 취소](cancel-machine-action.md)

###### [권장 사항]()
####### [권장 방법 및 속성](recommendation.md)
####### [모든 권장 사항 목록](get-all-recommendations.md)
####### [ID별 권장 사항 가져오기](get-recommendation-by-id.md)
####### [소프트웨어별 권장 사항 가져오기](list-recommendation-software.md)
####### [권장 사항별 컴퓨터 목록](get-recommendation-machines.md)
####### [권장 사항별 취약성 목록](get-recommendation-vulnerabilities.md)

###### [수정 작업]()
####### [수정 작업 방법 및 속성](get-remediation-methods-properties.md)
####### [ID로 수정 작업 1개 가져오기](get-remediation-one-activity.md)
####### [모든 수정 작업 나열s](get-remediation-all-activities.md)
####### [한 번의 수정 작업이 있는 노출된 장치 목록](get-remediation-exposed-devices-activities.md)

###### [점수]()
####### [점수 방법 및 속성](score.md)
####### [컴퓨터 그룹별 노출 점수 목록](get-machine-group-exposure-score.md)
####### [노출 점수 가져오기](get-exposure-score.md)
####### [장치 보안 점수 가져오기](get-device-secure-score.md)

###### [소프트웨어]()
####### [소프트웨어 방법 및 속성](software.md)
####### [소프트웨어 목록](get-software.md)
####### [ID별 소프트웨어 가져오기](get-software-by-id.md)
####### [소프트웨어 버전 배포 목록](get-software-ver-distribution.md)
####### [소프트웨어별 컴퓨터 목록](get-machines-by-software.md)
####### [소프트웨어별 취약성 목록](get-vuln-by-software.md)
####### [누락된 KB 가져오기](get-missing-kbs-software.md)

###### [사용자]()
####### [사용자 방법](user.md)
####### [사용자 관련 경고 가져오기](get-user-related-alerts.md)
####### [사용자 관련 컴퓨터 가져오기](get-user-related-machines.md)

###### [취약성]()
####### [취약성 방법 및 속성](vulnerability.md)
####### [취약성 목록](get-all-vulnerabilities.md)
####### [컴퓨터 및 소프트웨어별 취약성 목록](get-all-vulnerabilities-by-machines.md)
####### [ID별 취약성 가져오기](get-vulnerability-by-id.md)
####### [취약성별 컴퓨터 목록](get-machines-by-vulnerability.md)

##### [API 사용 방법 - 샘플]()
###### [Power Automate](api-microsoft-flow.md)
###### [Power BI](api-power-bi.md)
###### [Python을 사용하는 지능형 헌팅](run-advanced-query-sample-python.md)
###### [PowerShell을 사용하는 지능형 헌팅](run-advanced-query-sample-powershell.md)
###### [OData 쿼리 사용](exposed-apis-odata-samples.md)


#### [원시 데이터 스트리밍 API]()
##### [원시 데이터 스트리밍](raw-data-export.md)
##### [Azure 이벤트 허브에 지능형 헌팅 이벤트 스트리밍](raw-data-export-event-hub.md)
##### [저장소 계정에 지능형 헌팅 이벤트 스트리밍](raw-data-export-storage.md)


#### [SIEM 통합]()
##### [엔드포인트용 Microsoft Defender를 사용하여 SIEM 도구 통합](configure-siem.md)
##### [엔드포인트용 Microsoft Defender 검색 필드](api-portal-mapping.md)
##### [SIEM REST API를 사용하여 검색 결과 끌어오기](pull-alerts-using-rest-api.md)
##### [SIEM 도구 통합 문제 해결](troubleshoot-siem.md)

#### [파트너 및 API]()
##### [파트너 응용 프로그램](partner-applications.md)
##### [연결된 응용 프로그램](connected-applications.md)
##### [API 탐색기](api-explorer.md)

#### [역할 기반 액세스 제어]()
##### [RBAC를 사용하여 포털 액세스 관리](rbac.md)
##### [역할 만들기 및 관리](user-roles.md)
##### [장치 그룹 만들기 및 관리]()
###### [장치 그룹 사용](machine-groups.md)
###### [장치 태그 만들기 및 관리](machine-tags.md)







### [MSSP(관리형 보안 서비스 공급자) 통합]()
#### [관리형 보안 서비스 공급자 통합 구성](configure-mssp-support.md)
#### [관리되는 보안 서비스 공급자 지원](mssp-list.md)
#### [MSSP 액세스를 포털에 부여](grant-mssp-access.md)
#### [MSSP 고객 포털에 액세스](access-mssp-portal.md)
#### [경고 알림 구성](configure-mssp-notifications.md)
#### [파트너 응용 프로그램에 액세스하기](exposed-apis-create-app-partners.md)
#### [고객 테넌트에서 경고 페치](fetch-alerts-mssp.md)
#### [관리형 보안 서비스 공급자 기회](mssp-support.md)
### [파트너 통합 시나리오]()
#### [기술 파트너 기회](partner-integration.md)
#### [엔드포인트용 Microsoft Defender 파트너 자격](get-started-partner-integration.md) 
### [통합]()
#### [엔드포인트용 Microsoft Defender 통합](threat-protection-integration.md)
#### [조건부 액세스로 사용자, 데이터 및 장치 보호](conditional-access.md)
#### [Microsoft Cloud App Security 통합 개요](microsoft-cloud-app-security-integration.md)

### [Windows의 정보 보호 개요]()
#### [Windows 통합](information-protection-in-windows-overview.md)

### [엔드포인트용 Microsoft Defender 커뮤니티에 액세스](community.md) 

### [유용한 리소스](helpful-resources.md)

## [문제 해결]()
### [센서 상태 문제 해결]()
#### [센서 상태 확인](check-sensor-status.md)
#### [비정상적인 센서 수정](fix-unhealthy-sensors.md)
#### [비활성 장치](fix-unhealthy-sensors.md#inactive-devices)
#### [잘못 구성된 장치](fix-unhealthy-sensors.md#misconfigured-devices)
#### [이벤트 뷰어로 컴퓨터에서 센서 이벤트 및 오류 검토](event-error-codes.md)

### [클라이언트 분석기를 사용한 센서 상태 문제 해결]()
#### [클라이언트 분석기 개요](overview-client-analyzer.md)
#### [클라이언트 분석기 다운로드 및 실행](download-client-analyzer.md)
#### [Windows에서 클라이언트 분석기 실행](run-analyzer-windows.md)
#### [macOS 또는 Linux에서 클라이언트 분석기 실행](run-analyzer-macos-linux.md)
#### [Windows에서 고급 문제 해결을 위한 데이터 수집](data-collection-analyzer.md)
#### [분석기 HTML 보고서 이해](analyzer-report.md)
#### [클라이언트 분석기 도구에 대한 피드백 제공](analyzer-feedback.md)

 

### [엔드포인트용 Microsoft Defender 서비스 문제 해결]()
#### [서비스 문제 해결](troubleshoot-mdatp.md)
#### [서비스 상태 확인](service-status.md)
#### [엔드포인트용 Microsoft Defender 지원 문의](contact-support.md) 

### [실시간 대응 문제 해결](troubleshoot-live-response.md)

### [LiveAnalyzer를 사용하여 지원 로그 수집](troubleshoot-collect-support-log.md)

### [공격 표면 축소 문제 해결]()
#### [네트워크 보호](troubleshoot-np.md)
#### [공격 표면 감소 규칙](troubleshoot-asr.md)
#### [공격 표면 감소 규칙으로 마이그레이션](migrating-asr-rules.md)

# [Microsoft 365 Defender](../defender/index.yml)
# [Office 365용 Defender](../office-365-security/index.yml)
# [ID용 Defender](/defender-for-identity/)
