# Protein Fruit

Unity로 개발한 뱀서라이크 2D 서바이벌 게임입니다.

## 장르 및 테마
과일 vs 채소 / 생존 시간에 따라 재화(단백질) 획득

## 사용 기술
- Unity 2022.3 LTS / C#
- New Input System
- ShaderLab / HLSL (커스텀 셰이더)

## 구현 내용

### 아키텍처
- DontDestroyOnLoad 기반 매니저 싱글톤 구조 (GameManager, PoolManager, UIManager 등)
- GameState FSM으로 씬 전환 및 TimeScale 제어

### 주요 시스템
- 오브젝트 풀링 — 적, 투사체, 경험치, 히트 이펙트 전체 풀링 적용
- 스킬 시스템 — ProjectileSkill, AreaSkill, AuraSkill, OrbitSkill 계층 구조
- 보스 패턴 시스템 — Charge / AreaAttack / Projectile / Summon 4종 패턴 + 페이즈 관리
- 무한 맵 — 3x3 청크 재배치 방식
- 캐릭터 강화/해금 시스템 — PlayerPrefs 기반 영구 저장

### 성능 최적화
- OverlapCircleNonAlloc + Collider2D[32] 버퍼로 GC 방지
- Animator 파라미터 해시 캐싱
- 이벤트 기반 UI 갱신 (폴링 방지)

## 리팩토링 예정
- MapManager 청크 오브젝트 풀링 적용
- Boss 클래스 Composition 패턴 전환 고려

## 개발 현황
현재 미완성 상태이며, 추후 완성 예정입니다.
