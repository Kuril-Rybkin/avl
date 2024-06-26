# avl
## Task specification

The task is to implement the template Bestsellers parameterized by the Product type which is used as an identification of individual products. The Product type has a copy constructor (and a copy assignment operator), destructor, comparison operators and a specialization of std::hash. The class Bestsellers must implement the following public methods:

- `size_t products() const` returns the number of different product types on record (not the number of pieces sold),
- `void sell(const Product& p, size_t amount)` records selling amount pieces of product p,
- `size_t rank(const Product& p) const` returns the position of p in the list of all recorded product types sorted by pieces sold in descending order with indexing starting at 1 (rank(p) = 1 for the best-selling product p); if there are more product types with the same number of pieces sold, you can order them arbitrarily,
- `const Product& product(size_t rank) const` inverse function to rank (unless an exception occurs, it holds that product(rank(p)) == p and rank(product(r)) == r),
- `size_t sold(size_t r) const` number of pieces sold of the r-th best-selling product,
- `size_t sold(size_t from, size_t to) const` analogous to the single-parameter version, it returns the sum of pieces sold over the interval of ranks from `from` to `to` (including both endpoints; i.e., `sold(r, r) == sold(r)` and `sold(1, products())` is the total number of pieces sold over all products; input `to < from` is considered invalid).

Bonus only: `size_t first_same(size_t r) const` and `size_t last_same(size_t r) const` returns the smallest (resp. largest) rank x such that `sold(x) == sold(r)`. These methods are used only in the bonus test. If you are not solving the bonus test, leave the default implementation that always returns 0.

If any argument is invalid (i.e. rank is out of range or an unknown product is input to rank), raise the exception std::out_of_range.

### Conditions
- To obtain 1 point, the interface above must be implemented, but the implementation does not need to be too efficient.
- To obtain 3.5 points, the implementation must be efficient if the number of pieces sold are random, but the complexity of the method `sold(from, to)` can depend on to - from (linear).
- To obtain 7 points, the implementation must be efficient, the complexity of the method `sold(from, to)` can still depend on to - from (linear).
- To obtain 10 points, the method `sold(from, to)` must be efficient even for large to - from (logarithmic).
- Bonus: To obtain 12 points, you must correctly and efficiently implement the methods first_same and last_same.

---

The solution uploaded here was awarded the full 12 points.
