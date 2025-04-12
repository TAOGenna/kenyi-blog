## Never forget
- If you want to test locally use the localhost
- If you are about to push your commits to Github comment the one with localhost and leave the first line uncommented
```
baseURL: "https://taogenna.github.io/kenyi-blog/"
# baseURL: "http://localhost:1313"
```

## How to create a new blog 
```
hugo new docs/<name of the post>/<name of the post>.md
```
## How to build your site

```
hugo server
```
## Problems with inline equations or align? 

Usually use `{{< rawhtml >}}` works just fine. Example: 
```
{{< rawhtml >}}
$$

E_i = V^{(1)}(\mathbf{r}_i) + \frac{1}{2} \sum_{j} V^{(2)}(\mathbf{r}_i, \mathbf{r}_j) + \frac{1}{6} \sum_{j,k} V^{(3)}(\mathbf{r}_i, \mathbf{r}_j, \mathbf{r}_k) + \frac{1}{24} \sum_{j,k,l} V^{(4)}(\mathbf{r}_i, \mathbf{r}_j, \mathbf{r}_k, \mathbf{r}_l) + \cdots
$$ 
{{< /rawhtml >}}
```