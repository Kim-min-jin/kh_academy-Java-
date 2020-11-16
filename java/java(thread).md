# 용어 정리

퀸텀 타임(quantum time) - 시간 조각
시분할(time sharing)
여러 프로그램을 돌아가면서 실행 -> 스케줄링

물리적으로 동시에 돌아감 -> 병렬성(pararalism)
실제로 동시에 돌아가는 것처럼 보임 -> 동시성(concurrency)

# 스레드 사용의 문제점

- 동기화(synchronzation) 문제
- 임계영역(ciritical section) 문제

# 스레드의 상태
- NEW : 새로 생성된 경우
- RUNNABLE : 실행 대기
- 실행
- 일시정지
- 종료

## start() 메서드가 실행된 경우
 