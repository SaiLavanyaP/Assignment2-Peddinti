# Assignment2-Peddinti
# Sai Lavanya Peddinti
######  Eiffel Tower/Paris
It is one of my favourite place since childhood . **Eiffel Tower** is known for being one of the most beautiful and has been a powerful and __distinctive symbol__ of the city of Paris in the world. The Eiffel Tower took the name of its creator, Gustave Eiffel.

***

Above used horizontal rule...
## Directions to reach MO to Paris using ordered List
1. Take a rental car or cab to reach nearest airport i.e, Kansas from Maryville.
2. Fly from Kansas to France Orly Airport(ORY) for about 12hours via Qatar Airways.
3. After reaching Orly Airport, use any below mode of transport to reach Paris city center
    1. Bus
    2. Train
    3. Taxi
4. I choose bus mode for better city view and will reach Paris.
 - List of items to be carried to chill out while travelling
 - Reading novels
 - Snacks and drinks
 - Electronic gadgets

[AboutMe](AboutMe.md)


***

# Food/Drinks List

Below table gives the list of food and drink item list
|*Name*|*Location*|*Cost*|
| --- | --- | --- |
| Chicken wings |Zen| $5 |
| KFC Nuggets | Maryville| $10 |
| Monster Energy drink | Walmart| $1.5|
| Pepsi | Walmart| $1.00|

***

# Pity Quotes
>"And now that you don't have to be perfect, you can be good." —*John Steinbeck*

>“Life is never fair, and perhaps it is a good thing for most of us that it is not.” —*Oscar Wilde*

***

# Code Fencing
> We are given a directed graph. We need to compute whether the graph has a negative cycle or not. A negative cycle is one in which the overall sum of the cycle becomes negative.

Link for the Detect a negative cycle in a Graph
<https://www.geeksforgeeks.org/detect-negative-cycle-graph-bellman-ford/>

```
struct Edge {
    int a, b, cost;
};

int n, m;
vector<Edge> edges;
const int INF = 1000000000;

void solve()
{
    vector<int> d(n);
    vector<int> p(n, -1);
    int x;
    for (int i = 0; i < n; ++i) {
        x = -1;
        for (Edge e : edges) {
            if (d[e.a] + e.cost < d[e.b]) {
                d[e.b] = d[e.a] + e.cost;
                p[e.b] = e.a;
                x = e.b;
            }
        }
    }

    if (x == -1) {
        cout << "No negative cycle found.";
    } else {
        for (int i = 0; i < n; ++i)
            x = p[x];

        vector<int> cycle;
        for (int v = x;; v = p[v]) {
            cycle.push_back(v);
            if (v == x && cycle.size() > 1)
                break;
        }
        reverse(cycle.begin(), cycle.end());

        cout << "Negative cycle: ";
        for (int v : cycle)
            cout << v << ' ';
        cout << endl;
    }
}
```

Link for the source code:
<https://cp-algorithms.com/graph/finding-negative-cycle-in-graph.html>

