# assignment2-Bekkari
Assignment 2 of Web Apps

# AKSHITHA BEKKARI
###### Hyderabad

I am more **connected** to that place as it's my hometown and lot of **memories** are bound with it. And I loved it for it's food, places which gives me some pleasant feeling. Also, It's a home for multicultural and multidiversity where each individual get along well.

----

### DIRECTIONS FROM MARYVILLE TO HYDERABAD
1. Travel From Maryville to my favourite place
   1. By Cab from Maryville to Kansas City
   2. By Flight from Kansas City to Chicago
   3. By Flight from Chicago to Delhi
   4. By Flight from Delhi to Hyderabad 
2. Finally reached to my favourite place!
* Playing Cards
* Bluetooth Speaker
* Snacks
* Comfy Clothes
* Firewood
* Camping Tent

[AboutMe](AboutMe.md)

-------

#### NEW SECTION FOR FOOD ITEMS
Food Items that I would recommend to try and the cost that one should afford for each item in respective places.
|Item|Place|Cost|
|-----|-----|-----:|
|Chicken Biryani|Hyderabad|$4|
|Vada Pav|Mumbai|$2|
|Pani puri|Kolkata|$3|
|Dosa|Bangalore|$1|

--------

#### QUOTES
> "Don't feel stupid if you don't like what everyone else pretends to love" - *Emma Watson*

> "When people throw stones at you, covert them into milestones" - *Sachin Tendulkar*

----------

#### CODE FENCING
> A divide-and-conquer algorithm recursively breaks down a problem into two or more sub-problems of the same or related type, until these become simple enough to be solved directly.

Link for the algorithm description <https://en.wikipedia.org/wiki/Divide-and-conquer_algorithm>
```
int m, n;
vector<long long> dp_before(n), dp_cur(n);

long long C(int i, int j);

// compute dp_cur[l], ... dp_cur[r] (inclusive)
void compute(int l, int r, int optl, int optr) {
    if (l > r)
        return;

    int mid = (l + r) >> 1;
    pair<long long, int> best = {LLONG_MAX, -1};

    for (int k = optl; k <= min(mid, optr); k++) {
        best = min(best, {(k ? dp_before[k - 1] : 0) + C(k, mid), k});
    }

    dp_cur[mid] = best.first;
    int opt = best.second;

    compute(l, mid - 1, optl, opt);
    compute(mid + 1, r, opt, optr);
}

int solve() {
    for (int i = 0; i < n; i++)
        dp_before[i] = C(0, i);

    for (int i = 1; i < m; i++) {
        compute(0, n - 1, 0, n - 1);
        dp_before = dp_cur;
    }

    return dp_before[n - 1];
}
```
Link to the Algorithm code source <https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html>