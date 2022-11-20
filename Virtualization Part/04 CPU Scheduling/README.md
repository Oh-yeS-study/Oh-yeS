# Virtualization 
## 04 CPU Scheduling

---
## Q&A
### Round-Robin과 Time slice는 무슨 관계일까❓
Time slice를 줄이게 되면, 응답 시간은 줄어들게 된다. 그러나 작업의 교체가 빈번하게 이뤄지므로 context switching 비용이 늘어난다는 단점이 있다.

반대로, time slice를 키우면, 응답 시간도 늘어나게 된다. 그러나 context switching 비용은 줄어든다.

이런 특성이 있기 때문에 두 개의 값을 비교하여 적절한 값을 선택해야 한다.
