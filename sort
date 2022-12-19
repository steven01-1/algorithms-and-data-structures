/*
 * ************
 * insertion sort
 * ************
 */
// index [l, r]
// for array[N]
template <typename Type> void insertion_sort(Type *array, int l, int r) {
  for (int i = l + 1; i <= r; ++i) {
    Type key = array[i];
    int j = i - 1;
    while ( j >= l && array[j] > key) {
      array[j + 1] = array[j];
      --j;
    }
    array[j + 1] = key;
  }
}


/*
 * ************
 * merge sort
 * ************
 */
// index [first, last]
// replace N
// for array[N]
template <typename Type> void merge_sort(Type *array, int first, int last) {
  if (last - first + 1 <= N) 
    insertion_sort(array, first, last);
  else {
    int midpoint = (first + last) / 2;
    // start from index 1
    merge_sort(array, first, midpoint);
    merge_sort(array, midpoint + 1, last);
    merge(array, first, midpoint, last);
  }
}

template <typename Type> void merge(Type *array, int first, int midpoint, int last) {
  int nl = midpoint - first + 1;
  int nr = last - midpoint;
  Type ary1[nl + 1];
  Type ary2[nr + 1];
  ary1[nl] = std::numeric_limits<int>::max();
  ary2[nr] = std::numeric_limits<int>::max();
  for (int i = 0; i < nl; ++i) 
    ary1[i] = array[first + i];
  for (int i = 0; i < nr; ++i)
    ary2[i] = array[midpoint + 1 + i];
  int il = 0, ir = 0;
  for (int i = first; i <= last; ++i) {
    if (ary1[il] <= ary2[ir]) 
      array[i] = ary1[il++];
    else 
      array[i] = ary2[ir++];
  }
}
