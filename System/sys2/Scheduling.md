## Scheduling

### Tache :

* Deadline
* Temp d’exec
* Dépendances
* (Priorité)

### Batch

* Turnaround time
* Throughtput

Taches plus longues = plus tard

* FCFS first come first serve
* STF shortest first

Time-sharing

* Plusieurs taches en même temps

```mermaid
graph RL
	A((New)) --> B((Ready))
	B((Ready)) --> C((Run))
	C((Run)) --> D((Wait))
	C((Run)) --> B((Ready))
	D((Wait)) --> B((Ready))
	C((Run)) --> E((Dead))
```



bottleneck

* cpu bound
* io bound
* memory bound