# Virtualization 
## 05 Multi-level Feedback

---
## Q&A
### MLFQ에서 작업의 time slice가 끝나기 전에 CPU를 양보하여 우선 순위를 유지시키는 것을 어떻게 막을 수 있을까❓
1. 작업이 주어진 단계에서 time slice를 모두 소진하면, 우선 순위를 낮추고
2. 일정시간 S가 지나면, 시스템의 모든 작업의 우선 순위를 최상위 단계로 올린다.
   - 여기서 S는 너무 길면, starving이 발생할 수 있고, 너무 짧으면, 성능이 떨어질 수 있다. 이렇게 값을 결정하기 힘든 상수를 voo-doo constant라고 한다.
