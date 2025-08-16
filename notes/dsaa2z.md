# Array

Left rotate an array by D places

```
void rotate(vector<int>& nums, int k) {
    k=k%nums.size();
    reverse(nums.begin(),nums.end());
    reverse(nums.begin(),nums.begin()+k);
    reverse(nums.begin()+k,nums.end());
}
```

Find missing number in an array

```
int missingNumber(vector<int>& nums) {
    int sum=0,n=nums.size();
    for(int i=0;i<n;i++){
        sum+=nums[i];
    }
    return ((n*(n+1))/2)-sum;
}
```
```
int missingNumber(vector<int>& a) {
    int n=a.size(),x=n;
    for(int i=0;i<n;i++) x^=i^a[i];
    return x;
}
```
Maximum Consecutive Ones

```
int findMaxConsecutiveOnes(vector<int>& a) {
    int c=0,r=0;
    for(auto it:a){
        if(it==0) r=max(r,c),c=0;
        else c++;
    }
    r=max(r,c);
    return r;
}
```
Element appears twice except one
```
int singleNumber(vector<int>& a) {
    int r=0;
    for(auto it:a) r=r^it;
    return r;
}
```
Longest Subarray with given Sum K (Positives)

```
int longestSubarrayWithSumK(vector<int> a, long long k) {
    int ma=0,l=0,r=0,n=a.size();
    long long s=a[0];
    while(r<n){
        while(l<=r && s>k){
            s-=a[l++];
        }
        if(s==k) ma=max(ma,r-l+1);
        r++;
        if(r<n){
           s+=a[r];
        }
    }
    return ma;
}
```
Longest Subarray with sum K (Postives and Negatives)
```
int getLongestSubarray(vector<int>& a, int k){
    unordered_map<int,int> mp;
    int s=0,ma=0;
    mp[0]=-1;
    for(int i=0;i<a.size();i++){
        s+=a[i];
        if(mp.find(s-k)!=mp.end()) ma=max(ma,i-mp[s-k]);
        if(mp.find(s)==mp.end()) mp[s]=i;
    }
    return ma;
}
```
Two Sum
```
vector<int> twoSum(vector<int>& a, int t) {
        vector<int> res;
    unordered_map<int,int> mp; 
    for(int i=0;i<a.size();i++){
        if(mp.find(t-a[i])!=mp.end()){
            res.push_back(i);
            res.push_back(mp[t-a[i]]);
        }
        mp[a[i]]=i;
    }
    return res;
}
```
Sort an array of 0s, 1s and 2s
```
void sortColors(vector<int>& a) {
    int n=a.size();
    int z=0,o=0,t=n-1;
    while(o<=t){
        if(a[o]==0) swap(a[z++],a[o++]);
        else if(a[o]==2) swap(a[t--],a[o]);
        else o++;
    }
}
```
Majority Element (>n/2 times)
```
int majorityElement(vector<int>& a) {
    int v=INT_MAX,c=0;
    for(auto it:a){
        if(it==v) c++;
        else{
            if(!c) v=it;
            else c--;
        }
    }
    return v;
}
```
Majority Element (n/3 times)
```
vector<int> majorityElement(vector<int>& nums) {
    int num1=-1,num2=-1,count1=0,count2=0;
    for(auto it:nums){
        if(it==num1) count1++;
        else if(it==num2) count2++;
        else if(!count1) {num1=it;count1=1;}
        else if(!count2) {num2=it;count2=1;}
        else {count1--;count2--;}
    }
    count1=0,count2=0;
    for(auto it:nums){
        if(it==num1) count1++;
        else if(it==num2) count2++;
    }
    vector<int> res;
    if(count1>(nums.size()/3)) res.push_back(num1);
    if(count2>(nums.size()/3)) res.push_back(num2);
    return res;
}
```
Kadane's Algorithm
```
int maxSubArray(vector<int>& a) {
    int sum=0,ans=INT_MIN;
    for(auto it:a){
        sum+=it;
        ans=max(ans,sum);
        if(sum<0) sum=0;
    }
    return ans;
}
```
Stock Buy and Sell
```
int maxProfit(vector<int>& a) {
    int mi=a[0],ma=a[0],ans=INT_MIN;
    for(int i=0;i<a.size();i++){
        if(a[i]<mi) mi=ma=a[i];
        if(a[i]>ma) ma=a[i];
        ans=max(ans,ma-mi);
    }
    return ans;
}
```
Rearrange Array Elements by Sign
```
vector<int> rearrangeArray(vector<int>& nums) {
    vector<int> ans(nums.size(),0);
    int a=0,b=1;
    for(int i=0;i<nums.size();i++){
        if(nums[i]>=0){
            ans[a]=nums[i];
            a+=2;
        }
        else{
            ans[b]=nums[i];
            b+=2;
        }
    }
    return ans;
}
```
Next Permutation
```
void nextPermutation(vector<int>& nums) {
    int i;
    for(i=nums.size()-2;i>=0;i--) if(nums[i]<nums[i+1]) break;   
    if(i<0) reverse(nums.begin(),nums.end());
    else{
        int l;
        for(l=nums.size()-1;l>i;l--) if(nums[l]>nums[i]) break;
        swap(nums[i],nums[l]);
        reverse(nums.begin()+i+1,nums.end());
    }
}
```
Longest Consecutive Sequence
```
int longestConsecutive(vector<int>& nums) {
    unordered_set<int> s(nums.begin(),nums.end());
    int res=0;
    for(auto i:nums){
        if(s.find(i)==s.end()) continue;
        s.erase(i);
        int p=i-1,n=i+1;
        while(s.find(p)!=s.end()) s.erase(p--);
        while(s.find(n)!=s.end()) s.erase(n++);
        res=max(res,n-p-1);
    }
    return res;
}
```
Set Matrix Zeroes
```
void setZeroes(vector<vector<int>>& m) {
    int r=m.size(),c=m[0].size();
    int row=1;
    for(int i=0;i<c;i++) if(m[0][i]==0) row=0;
    for(int i=0;i<r;i++) if(m[i][0]==0) m[0][0]=0;
    for(int i=1;i<r;i++){
        for(int j=0;j<c;j++){
            if(i==0 && j==0) continue;
            if(m[i][j]==0){
                m[0][j]=0;
                m[i][0]=0;
            }
        }
    }
    for(int i=1;i<r;i++){
        for(int j=1;j<c;j++){
            if(m[0][j]==0 || m[i][0]==0){
                m[i][j]=0;
            }
        }
    }
    for(int i=1;i<c;i++) if(row==0) m[0][i]=0;
    for(int i=0;i<r;i++) if(m[0][0]==0) m[i][0]=0;
    if(row==0) m[0][0]=0;
}
```
Rotate Matrix
```
void rotate(vector<vector<int>>& a) {
    int n=a.size();
    for(int i=1;i<n;i++) for(int j=0;j<i;j++) swap(a[i][j],a[j][i]);
    for(int i=0;i<n;i++) reverse(a[i].begin(),a[i].end());
}
```
Spiral Matrix
```
vector<int> spiralOrder(vector<vector<int>>& m) {
    vector<int> v;
    int x1=0,y1=0,x2=0,y2=m[0].size()-1,x3=m.size()-1,y3=m[0].size()-1,x4=m.size()-1,y4=0;
    while(x1<=x4 && y1<=y2){
        if(x1==x4){
            for(int i=y1;i<=y2;i++) v.push_back(m[x1][i]);
        }
        else if(y1==y2){
            for(int i=x1;i<=x4;i++) v.push_back(m[i][y1]);
        }
        else{
        for(int i=y1;i<y2;i++) v.push_back(m[x1][i]);
        for(int i=x2;i<x3;i++) v.push_back(m[i][y2]);
        for(int i=y3;i>y4;i--) v.push_back(m[x3][i]);
        for(int i=x4;i>x1;i--) v.push_back(m[i][y4]);
        }
        x1++,y1++,x2++,y2--,x3--,y3--,x4--,y4++;
    }
    return v;
}
```
Count subarrays with given sum
```
int subarraySum(vector<int>& a, int t) {
    int s=0,c=0;
    unordered_map<int,int> mp;
    mp[0]++;
    for(auto it:a){
        s+=it;
        c+=mp[s-t];
        mp[s]++;
    }
    return c;
}
```
Pascal's Triangle
```
vector<vector<int>> generate(int n) {
    vector<vector<int>> ans(n);
    ans[0].push_back(1);
    if(n==1) return ans;
    ans[1].push_back(1);
    ans[1].push_back(1);
    if(n==2) return ans;
    for(int i=2;i<n;i++){
        ans[i].push_back(1);
        for(int j=1;j<i;j++){
            ans[i].push_back(ans[i-1][j-1]+ans[i-1][j]);
        }
        ans[i].push_back(1);
    }
    return ans;
}
```
3 Sum
```
vector<vector<int>> threeSum(vector<int>& a) {
    vector<vector<int>> ans;
    int n=a.size();
    sort(a.begin(),a.end());
    for(int i=0;i<=n-3;i++){
        if(i>0 && a[i]==a[i-1]) continue;
        int j=i+1,k=n-1;
        while(j<k){
            if(a[i]+a[j]+a[k]==0){
                ans.push_back({a[i],a[j],a[k]});
                while (j<k && a[j]==a[j+1]) j++;
                while (j<k && a[k]==a[k-1]) k--;
                j++;k--;
            }
            else if(a[i]+a[j]+a[k]>0) k--;
            else j++;
        }
    }
    return ans;
}
```
4 Sum
```
vector<vector<int>> fourSum(vector<int>& a, int t) {
    sort(a.begin(),a.end());
    set<vector<int>> ans;
    vector<vector<int>> res;
    long long int v;
    if(a.size()<4) return res;
    for(int i=0;i<a.size()-3;i++){
        for(int j=i+1;j<a.size()-2;j++){
            int l=j+1,h=a.size()-1;
            while(l<h){
                v=a[i],v+=a[j],v+=a[l],v+=a[h];
                if(v<t) l++;
                else if(v>t) h--;
                else ans.insert({a[i],a[j],a[l++],a[h--]});
            } 
        }
    }
    for(auto it:ans) res.push_back(it);
    return  res;
}
```
Count subarrays with given XOR
```
int subarraysWithXorK(vector<int> a, int k) {
    int n = a.size(); 
    int xr = 0;
    map<int, int> mp; 
    mp[xr]++; 
    int c = 0;
    for (int i = 0; i < n; i++) {
        xr = xr ^ a[i];
        int x = xr ^ k;
        c+= mp[x];
        mp[xr]++;
    }
    return c;
}
```
Merge Overlapping Subintervals
```
vector<vector<int>> merge(vector<vector<int>>& a) {
    sort(a.begin(),a.end());
    int start=a[0][0],end=a[0][1];
    vector<vector<int>> res;
    for(int i=0;i<a.size();i++){
        if(end>=a[i][0]) end=max(end,a[i][1]);
        else{
            res.push_back({start,end});
            start=a[i][0];
            end=a[i][1];
        }
    }
    res.push_back({start,end});
    return res;
}
```
Merge Sorted Arrays Without Extra Space
```
void merge(vector<int>& a1, int m, vector<int>& a2, int n) {
    int i=m-1,j=n-1,k=m+n-1;
    while(i>=0 && j>=0){
        if(a2[j]>a1[i]) a1[k--]=a2[j--];
        else a1[k--]=a1[i--];
    }
    while(j>=0) a1[k--]=a2[j--];
}
```
Find the repeating and missing numbers
```
```

Count inversions
```
int merge(vector<int> &arr, int low, int mid, int high) {
    vector<int> temp;
    int left = low;
    int right = mid + 1;
    int cnt = 0;
    while (left <= mid && right <= high) {
        if (arr[left] <= arr[right]) {
            temp.push_back(arr[left]);
            left++;
        }
        else {
            temp.push_back(arr[right]);
            cnt += (mid - left + 1); //Modification 2
            right++;
        }
    }
    while (left <= mid) temp.push_back(arr[left++]);
    while (right <= high) temp.push_back(arr[right++]);
    for (int i = low; i <= high; i++) {
        arr[i] = temp[i - low];
    }
    return cnt; 
}

int mergeSort(vector<int> &arr, int low, int high) {
    int cnt = 0;
    if (low >= high) return cnt;
    int mid = (low + high) / 2 ;
    cnt += mergeSort(arr, low, mid);
    cnt += mergeSort(arr, mid + 1, high);
    cnt += merge(arr, low, mid, high);
    return cnt;
}
```

Reverse Pairs
```
int merge(vector<int>& arr,int l,int m,int r){
    int i=l,j,count=0;
    for(j=m+1;j<=r;j++){
        while(i<=m && arr[i]<=2LL*arr[j]) i++;
        count+=(m+1-i);
    }
    int d[r-l+1];
    i=l,j=m+1;
    int k=0;
    while(i<=m && j<=r){
        if(arr[i]<=arr[j]) d[k++]=arr[i++];
        else d[k++]=arr[j++];
    }
    while(i<=m) d[k++]=arr[i++];
    while(j<=r) d[k++]=arr[j++];
    k=0;
    for(int i=l;i<=r;i++) arr[i]=d[k++];
    return count;
}

int mergeSort(vector<int>& arr,int l,int r){
    if(l==r) return 0;
    int count=0;
    int m=l+(r-l)/2;
    count+=mergeSort(arr,l,m);
    count+=mergeSort(arr,m+1,r);
    count+=merge(arr,l,m,r);
    return count;
}
```
Maximum Product Subarray
```
int maxProduct(vector<int>& a) {
    int mi=1,ma=1,v,r=INT_MIN;
    for(auto it:a){
        v=max({it,it*mi,it*ma});
        mi=min({it,it*mi,it*ma});
        ma=v;
        r=max(r,ma);
    }
    return r;
}
```

# Binary Search

Search an Element

```
int search(vector<int>& a, int t) {
    int l=0,r=a.size()-1,m;
    while(l<=r){
        m=(l+r)/2;
        if(a[m]<t) l=m+1;
        else if(a[m]>t) r=m-1;
        else return m;
    }
    return -1;
}
```
Lower Bound 
```
int lowerBound(vector<int> arr, int n, int x) {
    int low = 0, high = n - 1;
    int ans = n;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] >= x)  ans = mid, high = mid - 1;
        else low = mid + 1;
    }
    return ans;
}
```
Upper Bound
```
int upperBound(vector<int> &arr, int x, int n) {
    int low = 0, high = n - 1;
    int ans = n;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] > x) ans = mid, high = mid - 1;
        else low = mid + 1;
    }
    return ans;
}
```
Floor and Ceil
```
int findFloor(int arr[], int n, int x) {
	int low = 0, high = n - 1;
	int ans = -1;
	while (low <= high) {
		int mid = (low + high) / 2;
		if (arr[mid] <= x) ans = arr[mid], low = mid + 1;
		else high = mid - 1;
	}
	return ans;
}

int findCeil(int arr[], int n, int x) {
	int low = 0, high = n - 1;
	int ans = -1;
	while (low <= high) {
		int mid = (low + high) / 2;
		if (arr[mid] >= x) ans = arr[mid], high = mid - 1;
		else low = mid + 1;
	}
	return ans;
}
```
First and Last Occurance
```
int firstOccurance(vector<int>& a, int t){
    int ans = -1, low = 0, high = a.size()-1, mid;
    while (low <= high) {
        mid = (low + high) / 2;
        if(a[mid] >= t) ans = mid, high = mid - 1;
        else low = mid + 1;
    }
    return ans;
}

int lastOccurance(vector<int>& a, int t){
    int ans = -1, low = 0, high = a.size()-1, mid;
    while (low <= high) {
        mid = (low + high) / 2;
        if(a[mid] <= t) ans = mid, low = mid + 1;
        else high = mid - 1;
    }
    return ans;
}
```
Search in Rotated Sorted Array (Unique values)

```
int search(vector<int>& arr, int k) {
    int low = 0, high = arr.size() - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == k) return mid;
        if (arr[low] <= arr[mid]) {
            if (arr[low] <= k && k < arr[mid]) high = mid - 1;
            else low = mid + 1;
        }
        else { 
            if (arr[mid] < k && k <= arr[high]) low = mid + 1;
            else high = mid - 1;
        }
    }
    return -1;
}
```
Search in Rotated Sorted Array (Duplicate values)
```
bool search(vector<int>&arr, int k) {
    int n = arr.size(); 
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == k) return true;
        if (arr[low] == arr[mid] && arr[mid] == arr[high]) {
            low = low + 1;
            high = high - 1;
        }
        else if (arr[low] <= arr[mid]) {
            if (arr[low] <= k && k < arr[mid]) {
                high = mid - 1;
            }
            else {
                low = mid + 1;
            }
        }
        else { 
            if (arr[mid] < k && k <= arr[high]) {
                low = mid + 1;
            }
            else {
                high = mid - 1;
            }
        }
    }
    return false;
}
```
Minimum in Rotated Sorted Array

```
int findMin(vector<int>& a) {
    int low = 0, high = a.size()-1, mid;
    while (low < high) {
        mid = (low + high) / 2;
        if (a[mid] > a[mid + 1]) return a[mid + 1];
        else if (a[low] < a[mid]) low = mid + 1;
        else high = mid;
    }
    return a[0];
}
```
Single element in a Sorted Array
```
int singleNonDuplicate(vector<int>& a) {
    if(a.size()==1 || a[0]!=a[1]) return a[0];
    if(a[a.size()-1] != a[a.size()-2]) return a[a.size()-1];
    int l=0,r=a.size()-1,m;
    while(l<=r){
        m=(l+r)/2;
        if(a[m-1]!=a[m] && a[m]!=a[m+1]) return a[m];
        else if((m%2==0 && a[m]==a[m+1])  || (m%2!=0 && a[m]==a[m-1])) l=m+1;
        else r=m-1;
    }
    return r;
}
```
Find Peak Element
```
int findPeakElement(vector<int>& a) {
    int n=a.size();
    if(n==1) return 0;
    if(a[0]>a[1]) return 0;
    if(a[n-1]>a[n-2]) return n-1;
    int l=1,r=n-2,m;
    while(l<=r){
        m=(l+r)/2;
        if(a[m-1]<a[m] && a[m]>a[m+1]) return m;
        else if(a[m-1]<a[m]) l=m+1;
        else r=m-1;
    }
    return -1;
}
```
Koko Eating Bananas
```
int minEatingSpeed(vector<int>& a, int h) {
    if(h<a.size()) return -1;
    int l=1,r=*max_element(a.begin(),a.end()),m;
    long long c=0;
    while(l<=r){
        m=(l+r)/2;
        c=0;
        for(int i=0;i<a.size();i++){
            c+=(a[i]/m);
            if(a[i]%m) c++;
        }
        if(c>h) l=m+1;
        else r=m-1;
    }
    return l;
}
```
Minimum Days to Make m Bouquets
```
int minDays(vector<int>& a, int b, int k) {
    if(a.size()/b<k) return -1;
    int l=0,r=*max_element(a.begin(),a.end()),m,c,v;
    while(l<=r){
        m=(l+r)/2;
        c=0;
        v=0;
        for(int i=0;i<a.size();i++){
            if(c==k){
                v++;
                c=0;
            } 
            if(a[i]<=m) c++;
            else c=0;
        }
        if(c==k) v++;
        if(v<b) l=m+1;
        else r=m-1;
    }
    return l;
}
```
Capacity To Ship Packages 
```
int shipWithinDays(vector<int>& a, int d) {
    int l=*max_element(a.begin(),a.end()),r=accumulate(a.begin(),a.end(),0),m,s,c;
    while(l<=r){
        m=(l+r)/2;
        s=0;
        c=1;
        for(auto it:a){
            s+=it;
            if(s>m){
                c++;
                s=it;
            }
        }
        if(c>d) l=m+1;
        else r=m-1;
    }
    return l;
}
```
Kth Missing Positive Number

```
int findKthPositive(vector<int>& a, int k) {
    int l=0,r=a.size()-1,m;
    while(l<=r){
        m=(l+r)/2;
        if(a[m]-m-1<k) l=m+1;
        else r=m-1;
    }
    return k+l;
}
```
Aggressive cows
```
bool canWePlace(vector<int> &stalls, int dist, int cows) {
    int n = stalls.size();
    int cntCows = 1;
    int last = stalls[0];
    for (int i = 1; i < n; i++) {
        if (stalls[i] - last >= dist) {
            cntCows++; //place next cow.
            last = stalls[i];
        }
        if (cntCows >= cows) return true;
    }
    return false;
}
int aggressiveCows(vector<int> &stalls, int k) {
    int n = stalls.size();
    sort(stalls.begin(), stalls.end());
    int low = 1, high = stalls[n - 1] - stalls[0];
    while (low <= high) {
        int mid = (low + high) / 2;
        if (canWePlace(stalls, mid, k) == true) low = mid + 1;
        else high = mid - 1;
    }
    return high;
}
```
Book Allocation
```
bool canAllocate(vector<int>& arr, int m, int threshold){
    int students = 1;
    int pages = 0;
    for (int i = 0; i < arr.size(); i++) {
        if (pages + arr[i] <= threshold) {
            pages += arr[i];
        }
        else {
            pages = arr[i];
            students++;
        }
    }
    return students <= m;
}

int findPages(vector<int>& arr, int n, int m) {
    if(m>n) return -1;
    int low = *max_element(arr.begin(),arr.end());
    int high = accumulate(arr.begin(),arr.end(),0);
    while (low <= high) {
        int mid = (low + high) / 2;
        if(canAllocate(arr,m,mid)) high = mid - 1;
        else high = low = mid + 1;
    }
    return low;
}
```
Split Array Largest Sum
```
bool f(vector<int>& a, int m,int k){
    int c=1,s=0;
    for(int i=0;i<a.size();i++){
        if(s+a[i]<=m){
            s+=a[i];
        }
        else{
            s=a[i];
            c++;
        }
    }
    return c<=k;
}

int splitArray(vector<int>& a, int k) {
    int l=*max_element(a.begin(),a.end()),r=accumulate(a.begin(),a.end(),0),m;
    while(l<=r){
        m=(l+r)/2;
        if(f(a,m,k)) r=m-1;
        else l=m+1;
    }
    return l;
}
```
Painter’s Partition
```
int countPainters(vector<int> &boards, int time) {
    int n = boards.size();
    int painters = 1;
    long long boardsPainter = 0;
    for (int i = 0; i < n; i++) {
        if (boardsPainter + boards[i] <= time) {
            boardsPainter += boards[i];
        }
        else {
            painters++;
            boardsPainter = boards[i];
        }
    }
    return painters;
}

int findLargestMinDistance(vector<int> &boards, int k) {
    int low = *max_element(boards.begin(), boards.end());
    int high = accumulate(boards.begin(), boards.end(), 0);
    while (low <= high) {
        int mid = (low + high) / 2;
        int painters = countPainters(boards, mid);
        if (painters <= k) high = mid - 1;
        else low = mid + 1;
    }
    return low;
}
```
Minimize Max Distance to Gas Station
```
```
Median of 2 sorted arrays
```
```
Kth element of 2 sorted arrays
```
```
Row with max 1s
```
int countOnes(vector<int> &row){
    int low = 0, high = row.size()-1, mid;
    while(low <= high) {
        mid = (low + high) / 2;
        if(row[mid] < row[mid+1]) {
            return row.size()-mid-1;
        }
        else if(row[mid] == 0) {
            low = mid + 1;
        }
        else {
            high = mid - 1;
        }
    }
    return row.size()-high-1;
}

int rowWithMax1s(vector<vector<int>> &matrix, int n, int m)
{
    int maxOnes = 0, maxOnesIndex = 0;
    for(int i = 0; i < n; i++) {
        if(matrix[i][0]==1 && maxOnes != m){
            maxOnes = m;
            maxOnesIndex = i;
        }
        else if(matrix[i][m-1]!=0){
            int rowOnes = countOnes(matrix[i]);
            if(rowOnes > maxOnes){
                maxOnes = rowOnes;
                maxOnesIndex = i;
            }
        }
    }
    return maxOnesIndex;
}
```
Search a 2D Matrix
```
bool searchMatrix(vector<vector<int>>& m, int t) {
    int r=m.size(),c=m[0].size(),l=0,h=r*c-1,mid,val;
    while(l<=h){
        mid=(l+h)/2;
        val=m[mid/c][mid%c];
        if(val==t) return true;
        else if(val<t) l=mid+1;
        else h=mid-1;
    }
    return false;
}
```
Search in a row and column wise sorted matrix
```
bool searchMatrix(vector<vector<int>>& matrix, int target) {
    int r=matrix.size(),c=matrix[0].size();
    int i=r-1,j=0;
    while(i>=0 && j<c){
        if(matrix[i][j]==target) return true;
        else if(matrix[i][j]<target) j++;
        else i--;
    }
    return false;
}
```
Find Peak Element (2D Matrix)
```
```
Matrix Median
```
```

# String

Remove Outermost Parentheses
```
string removeOuterParentheses(string s) {
    int c=0;
    string a;
    for(auto it:s){
        it=='('?c++:c--; 
        if((it!='(' || c!=1) && (it!=')' || c!=0)) a+=it;
    }
    return a;
}
```
Reverse Words in a String
```
string reverseWords(string s) {
    string t,a;
    for(auto it:s){
        if(it==' ') {if(t.size()) a=t+" "+a, t="";}
        else t+=it;
    }
    if(t.size()) a=t+" "+a;
    a.pop_back();
    return a;
}
```
Largest odd number in a string
```
string largestOddNumber(string num) {
    while(num.size()>0) 
        if((num[num.size()-1]-'0')%2!=0) return num; 
        else num.pop_back();
    return num;
}
```
Longest Common Prefix
```
string longestCommonPrefix(vector<string>& strs) {
    string ans="";
    int match=1;
    string base=strs[0];

    for(int i=0;i<base.size();i++){
        for(int j=1;j<strs.size();j++){
            if(strs[j][i]!=base[i]) match=0;
        }
        if(match) ans+=base[i];
        else break;
    }        
    return ans;
}
```
Isomorphic String
```
bool isIsomorphic(string s, string t) {
    unordered_map<char,char> mp1,mp2;
    for(int i=0;i<s.size();i++){
        if(mp1.find(t[i])!=mp1.end()) if(mp1[t[i]]!=s[i]) return false;
        if(mp2.find(s[i])!=mp2.end()) if(mp2[s[i]]!=t[i]) return false;
        mp1[t[i]]=s[i];
        mp2[s[i]]=t[i];
    }
    return true;
}
```
One string is a rotation of another
```
bool kmp(string s, int n){
    vector<int> lps(s.size(), 0);
    for(int i=1;i<lps.size();i++){
        int prev_idx = lps[i-1];
        while(prev_idx>0 && s[i] != s[prev_idx]){
            prev_idx = lps[prev_idx-1];
        }
        lps[i] = prev_idx + (s[i]==s[prev_idx] ? 1 : 0);
        if(lps[i]==n) return true;
    }
    return false;
}

bool rotateString(string s, string goal) {
    string str=goal+"#"+s+s;
    return kmp(str,s.size());
}
```
Valid Anagram
```
bool isAnagram(string s, string t) {
    int freq[26]={0},c=0;
    for(int i=0;i<s.size();i++){
        freq[s[i]-'a']++;
        c++;
    }
    for(int i=0;i<t.size();i++){
        freq[t[i]-'a']--;
        if(freq[t[i]-'a']>=0) c--;
        else return false;
    }
    if(c) return false;
    return true;
}
```
Sort Characters By Frequency
```
static bool comp(pair<int,char> a,pair<int,char> b){
    if(a.first>b.first) return true;
    return false;
}

string frequencySort(string s) {
    unordered_map<char,int> mp;
    for(auto it:s) mp[it]++;
    vector<pair<int,char>> v;
    for(auto it:mp) v.push_back({it.second,it.first});
    sort(v.begin(),v.end(),comp);
    string a;
    for(int i=0;i<v.size();i++){
        while(v[i].first--) a+=v[i].second;
    }
    return a;
}
```
Max Nesting Depth of the Parentheses
```
int maxDepth(string s) {
    int c=0,a=0;
    for(auto it:s){
        if(it=='(') c++;
        if(it==')') c--;
        a=max(a,c);
    }
    return a;
}
```
Roman to Integer
```
int r2n(char c){
    int x;
    c=='I'? x=1:c=='V'?x=5:c=='X'?x=10:c=='L'x=50:c=='C'?x=100:c=='D'?x=500:c=='M'?x=1000:x=0;
    return x;
}

int romanToInt(string s) {
    int x,y,sum=0,i;
    for (i=0; i<s.size(); i++) {
        x=r2n(s[i]);
        i!=s.size()-1?y=r2n(s[i+1]):y=0;
        if(x>=y) sum+=x;
        else{
            sum+=(y-x);
            i++;
        }
    }
    return sum;
}
```
Integer to Roman
```
string intToRoman(int num) {
    string ans="";
    int i=0;
    vector<int> nums={1000,900,500,400,100,90,50,40,10,9,5,4,1};
    vector<string> roman={"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
    while(num){
        if(num>=nums[i]){
            ans=ans+roman[i];
            num=num-nums[i];
        } 
        else{
            i++;
        }
    }
    return ans;
}
```
String to Integer (Atoi)
```
int myAtoi(string s) {
    int i=0,flag=1;
    int n=s.size();
    if(n==0) return 0;
    while(i<n && s[i]==' ') i++;
    if(i==n) return 0;
    if(s[i]=='-') flag=-1, i++;
    else if(s[i]=='+') i++;
    long int res=0;
    while(s[i]>='0' && s[i]<='9'){
        res=res*10;
        if(res>=INT_MAX || res<=INT_MIN) break;
        res=res+(s[i]-'0');
        i++;
    }
    if(flag==-1) res=res*flag;
    if(res<=INT_MIN) return INT_MIN;
    if(res>=INT_MAX) return INT_MAX;
    return res;
}
```
Count Number of Substrings
```
```
Longest Palindromic Substring
```
string longestPalindrome(string s) {
    vector<vector<bool>> dp(s.size(),vector<bool>(s.size(),false));
    int l=0,r=0;
    for(int i=0;i<s.size();i++){
        for(int j=0;j<s.size()-i;j++){
            if(i==0) dp[j][j]=true;
            else if(i==1 && s[j]==s[j+1]) dp[j][j+1]=true, l=j, r=j+i;
            else if(s[j]==s[j+i] && dp[j+1][j+i-1]){ dp[j][j+i]=true; if(i+1>r-l+1) l=j, r=j+i;}
        }
    }
    return s.substr(l,r-l+1);
}
```
Sum of Beauty of All Substrings
```
int beautySum(string s) {
    if(s.size()<3) return 0;
    vector<vector<int>> v(26,vector<int>(s.size()));
    v[s[0]-'a'][0]=1;
    for(int j=1;j<s.size();j++){
        for(int i=0;i<26;i++) v[i][j]=v[i][j-1];
        v[s[j]-'a'][j]++;
    }

    int a=0,mi,ma;
    for(int i=0;i<s.size()-2;i++){
        for(int j=i+2;j<s.size();j++){
            mi=501,ma=0;
            for(int k=0;k<26;k++){
                if(!v[k][j] || (i>0 && !(v[k][j]-v[k][i-1]))) continue;
                i==0?mi=min(mi,v[k][j]):mi=min(mi,v[k][j]-v[k][i-1]);
                i==0?ma=max(ma,v[k][j]):ma=max(ma,v[k][j]-v[k][i-1]);
            }
            a+=(ma-mi);
        }
    }
    return a;
}
```

Reverse Every Word in A String
```
string reverseWords(string s) {
    string t,a;
    for(auto it:s){
        if(it==' ') {if(t.size()) a=t+" "+a, t="";}
        else t+=it;
    }
    if(t.size()) a=t+" "+a;
    a.pop_back();
    return a;
}
```
Minimum number of bracket reversals				
```
int minAddToMakeValid(string s) {
    int c=0,n=0;
    for(auto it:s){
        it=='('?c++:c--;
        if(c<0) n++,c=0;
    }
    return c+n;
}
```
Count and say							
```
string countAndSay(int n) {
    int count=1;
    string s="1";
    string ans="";
    for(int i=0;i<n-1;i++){
        ans="";
        for(int j=0;j<s.size();j++){
            if(s[j]==s[j+1]){
                count++;
            }
            else{
                ans+=to_string(count);
                ans+=s[j];
                count=1;
            }
        }
        s="";
        s=ans;
    }
    return s;
}
```
Rabin Karp				
```
```
Z-Function				
```
```
KMP algo / LPS(pi) array				
```
int kmp(string s, int n){
    vector<int> lps(s.size(), 0);
    for(int i=1;i<lps.size();i++){
        int prev_idx = lps[i-1];
        while(prev_idx>0 && s[i] != s[prev_idx]){
            prev_idx = lps[prev_idx-1];
        }
        lps[i] = prev_idx + (s[i]==s[prev_idx] ? 1 : 0);
        if(lps[i]==n) return i-2*n;
    }
    return -1;
}

int strStr(string haystack, string needle) {
    string s=needle+"#"+haystack;
    return kmp(s,needle.size());
}
```
Shortest Palindrome				
```
```
Longest happy prefix				
```
```
Count palindromic subsequence 
```
```

# Linked List

Reverse LL 
```
ListNode* reverseList(ListNode* head) {
    if(!head) return NULL;
    if(!head->next) return head;
    ListNode *cur=head,*prv=NULL, *nxt;
    while(cur){
        nxt=cur->next;
        cur->next=prv;
        prv=cur;
        cur=nxt;
    }
    return prv;
}
```
```
ListNode* f(ListNode* head,ListNode* prev){
    if(!head) return prev;
    ListNode* temp=head->next;
    head->next=prev;
    return f(temp,head);
}

ListNode* reverseList(ListNode* head) {
    ListNode* prev=NULL;
    return f(head,prev);
}
```
Reverse DLL 
```
void reverse(node*&head) {
    node*temp = NULL;
    node*curr = head;
    while (curr != NULL)
    {
        temp = curr->prev;
        curr->prev = curr->next;
        curr->next = temp;          
        curr = curr->prev;
    }
    if(temp != NULL ) head = temp->prev;
}
```
Middle of the Linked List
```
ListNode* middleNode(ListNode* h) {
    if(!h->next) return h;
    ListNode *s=h,*f=h;
    while(f && f->next){
        s=s->next;
        f=f->next->next;
    }
    return s;
}
```
Linked List Cycle
```
bool hasCycle(ListNode *head) {
    ListNode *s=head,*f=head;
    while(f && f->next){
        s=s->next;
        f=f->next->next;
        if(s==f) return true;
    }
    return false;
}
```
Starting point in Linked List Cycle
```
ListNode *detectCycle(ListNode *head) {
    if(!head) return head;
    if(!head->next) return NULL;
    if(head->next==head) return head;
    ListNode *s=head,*f=head;
    while(f && f->next){
        s=s->next;
        f=f->next->next;
        if(s==f) break;
    }
    if(!f || !f->next) return NULL;
    s=head;
    while(s!=f){
        s=s->next;
        f=f->next;
    }
    return s;
}
```
Length of Loop in LL
```
int lengthOfLoop(Node *head) {
    if(!head) return 0;
    if(!head->next) return 0;
    if(head->next==head) return 1;
    Node *s=head,*f=head;
    while(f && f->next){
        s=s->next;
        f=f->next->next;
        if(s==f) break;
    }
    if(!f || !f->next) return 0;
    int c=1;
    f=s->next;
    while(s!=f){
        c++;
        f=f->next;
    }
    return c;
}
```
Palindrome 
```
ListNode* reverseiteration(ListNode* head){
    ListNode *curr=head,*prev=NULL,*nextptr=NULL;
    while(curr){
        nextptr=curr->next;
        curr->next=prev;
        prev=curr;
        curr=nextptr;
    }
    return prev;
} 

bool isPalindrome(ListNode* head) {
    ListNode *s=head,*f=head;
    while(f && f->next){
        s=s->next;
        f=f->next->next;
    }
    if(f) s=s->next;
    ListNode *temp=reverseiteration(s);
    while(temp){
        if(temp->val!=head->val) return false;
        temp=temp->next;
        head=head->next;
    }
    return true;
}
```
Segrregate Odd Even
```
ListNode* oddEvenList(ListNode* head) {
    if(!head || !head->next || !head->next->next) return head;
    ListNode* one=head,*two=head->next,*d=head->next->next,*t1=head,*t2=head->next;
    while(d){
        t1->next=d;
        t1=d;
        d=d->next;
        t2->next=d;
        t2=d;
        if(d) d=d->next;
    }
    t1->next=two;
    if(t2) t2->next=NULL;
    return one;
}
```
Remove Nth node from back
```
ListNode* removeNthFromEnd(ListNode* head, int n) {
    if(!head || !head->next) return NULL;
    ListNode* t=head;
    int count=0;
    while(t){
        count++;
        t=t->next;
    }
    if(count==n) return head->next;
    t=head;
    n=count-n;
    while(--n) t=t->next;
    if(t->next) t->next=t->next->next;
    return head;
}
```
Delete the Middle Node
```
ListNode* deleteMiddle(ListNode* head) {
    if(!head || !head->next) return NULL;
    ListNode *s=head,*f=head,*prv;
    while(f &&f->next){
        prv=s;
        s=s->next;
        f=f->next->next;
    }
    prv->next=prv->next->next;
    return head;
}
```
Sort 
```
ListNode* sortList(ListNode* head) {
    priority_queue<pair<int,ListNode *>,vector<pair<int,ListNode *>>,greater<pair<int,ListNode *>>> pq;
    ListNode *temp=new ListNode();
    while(head){
        pq.push({head->val,head});
        head=head->next;
    }
    head=temp;
    while(!pq.empty()){
        temp->next=pq.top().second;
        pq.pop();
        temp=temp->next;
    }
    temp->next=NULL;
    return head->next;
}
```
Sort a LL of 0's 1's and 2's
```
```
Intersection of Two Linked Lists
```
ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
    ListNode *temp=headA;
    while(temp->next){
        temp=temp->next;
    }
    temp->next=headA;
    
    ListNode *s=headB,*f=headB;
    while(f && f->next){
        s=s->next;
        f=f->next->next;
        if(s==f) break;
    }

    if(!f || !f->next) {
        temp->next=NULL;
        return NULL;
    }
    f=headB;
    while(s!=f){
        s=s->next;
        f=f->next;
    }
    temp->next=NULL;
    return s;
}
```
Add 1 to LL 
```
int f(Node *cur) {
    if(!cur) return 1;
    int sum=f(cur->next)+cur->data;
    cur->data=sum%10;
    return sum/10;
}

Node* addOne(Node *head) {
    Node *temp=head;
    int carry=f(head);
    if(carry){
        temp=new Node(1);
        temp->next=head;
    }
    return temp;
}
```
Add 2 numbers in LL
```
ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
    int k;
    ListNode* d=new ListNode();
    ListNode* ans=d;
    ListNode* prev=NULL;
    int c=0,sum=0;
    while(l1 && l2){
        sum=(l1->val+l2->val+c)%10;
        c=(l1->val+l2->val+c)/10;
        d->next=new ListNode(sum);
        l1=l1->next;
        l2=l2->next;
        d=d->next;
        prev=d;
    }
    if(l2){
        d->next=l2;
        while(l2){
            k=l2->val;
            l2->val=(l2->val+c)%10;
            c=(k+c)/10;
            prev=l2;
            l2=l2->next;
        }
    }
    else if(l1){
        d->next=l1;
        while(l1){
            k=l1->val;
            l1->val=(l1->val+c)%10;
            c=(k+c)/10;
            prev=l1;
            l1=l1->next;
        }
    } 
    if(c) prev->next=new ListNode(1);
    return ans->next;
}
```
Delete all occurrences of a key in DLL
```
```
Find pairs with given sum in DLL
```
```
Remove duplicates from sorted DLL
```
```
Reverse LL in group of given size K
```
```
Rotate a LL
```
ListNode* rotateRight(ListNode* head, int k) {
    if(head==NULL) return head;
    if(head->next==NULL) return head;
    int count=0;
    ListNode* temp=head,*temp2;
    while(temp!=NULL){
        count++;
        temp=temp->next;
    }
    k=k%count;
    k=count-k;
    temp=head;
    if(k==0) return head;
    while(--k){
        temp=temp->next; 
    }
    temp2=temp;
    while(temp->next!=NULL){
            temp=temp->next;
    }
    temp->next=head;
    head=temp2->next;
    temp2->next=NULL;
    return head;
}
```
Flattening of LL
```
```
Clone LL with Random Pointer
```
Node* copyRandomList(Node* head) {
    unordered_map<Node*,Node*> mp;
    Node* temp=head;
    while(temp){
        mp[temp]=new Node(temp->val);
        temp=temp->next;
    }
    temp=head;
    while(temp){
        mp[temp]->next=mp[temp->next];
        mp[temp]->random=mp[temp->random];
        temp=temp->next;
    }
    return mp[head];
}
```


# Recursion

All combintions without repetitions
```
#include <bits/stdc++.h>
using namespace std;

void f(vector<int> &a, vector<int> &ds, int ind){
    if(ind==a.size()){
        cout<<"[";
        for(auto it:ds) cout<<it<<" ";
        cout<<"]\n";
        return;
    }
    ds.push_back(a[ind]);
    f(a,ds,ind+1);
    ds.pop_back();
    f(a,ds,ind+1);
}

int main() {
    vector<int> a = {1,2,3};
    vector<int> ds;
    f(a, ds, 0);
    return 0;
}
```
All permutations without repetitions
```
#include <bits/stdc++.h>
using namespace std;

void f(vector<int> &a, vector<int> &ds, vector<bool> &vis, int ind){
    if(ind==ds.size()){
        cout<<"[";
        for(auto it:ds) cout<<it<<" ";
        cout<<"]\n";
        return;
    }
    for(int i=0;i<a.size();i++){
        if(!vis[i]){
            vis[i]=true;
            ds[ind]=a[i];
            f(a, ds, vis, ind+1);
            vis[i]=false;
        }
    }
}

int main() {
    
    vector<int> a = {1,2,3,4};
    vector<int> ds(a.size()); // size can be adjusted here
    vector<bool> vis(a.size(),false);
    f(a, ds, vis, 0);
    return 0;
}
```

All subarray Partitions
```
class Solution {
public:
    
    vector<vector<pair<int,int>>> v;
    vector<pair<int,int>> ds;
    
    void f(vector<int>& a, int ind){
        if(ind == a.size()){
            v.push_back(ds);
            return;
        }
        for(int i=ind;i<a.size();i++){
            ds.push_back({ind,i});
            f(a, i+1);
            ds.pop_back();
        }
    }
    
    double largestSumOfAverages(vector<int>& a, int k) {
        f(a, 0);
        for(auto it:v){
            for(auto jt:it){
                cout<<"["<<jt.first<<"-"<<jt.second<<"]"<<" ";
            }
            cout<<"\n";
        }
        return 0.0;
    }
};
```

# Bit Manipulation

# Stack and Queue

Next Greater Element I

```
vector<int> nextGreaterElement(vector<int>& n1, vector<int>& n2) {
    map<int,int> mp;
    stack<int> s;
    for(int i=n2.size()-1;i>=0;i--){
        while(!s.empty() && n2[i]>=s.top()) s.pop();
        if(!s.empty()) mp[n2[i]]=s.top();
        else mp[n2[i]]=-1;
        s.push(n2[i]);
    }
    vector<int> v;
    for(auto it:n1) v.push_back(mp[it]);
    return v;
}
```

Next Greater Element II

```
vector<int> nextGreaterElements(vector<int>& a) {
    int n=a.size();
    stack<int> s;
    vector<int> res(n,-1);
    for(int i=2*n-1;i>=0;i--){
        while(!s.empty() && a[i%n]>=s.top()) s.pop();
        if(!s.empty()) res[i%n]=s.top();
        s.push(a[i%n]);
    }
    return res;
}
```
Trapping Rain Water

```
int trap(vector<int>& a) {
    int n=a.size(),ma=0,ans=0,v;
    vector<int> l(a);
    vector<int> r(a);
    for(int i=0;i<n;i++){
        l[i]=ma;
        ma=max(ma,a[i]);
    }
    ma=0;
    for(int i=n-1;i>=0;i--){
        r[i]=ma;
        ma=max(ma,a[i]);
    }
    for(int i=0;i<n;i++){
        v=min(l[i],r[i])-a[i];
        if(v>0) ans+=v;
    }
    return ans;
}
```
Sum of Subarray Minimums
```
void left(vector<int> &l,vector<int> &h){
    stack<int> s;
    for(int i=0;i<h.size();i++){
        while(!s.empty() && h[i]<=h[s.top()]) s.pop();
        if(!s.empty()) l[i]=s.top();
        s.push(i);
    }
}

void right(vector<int> &r,vector<int> &h){
    stack<int> s;
    for(int i=h.size()-1;i>=0;i--){
        while(!s.empty() && h[i]<h[s.top()]) s.pop();
        if(!s.empty()) r[i]=s.top();
        s.push(i);
    }
}

int sumSubarrayMins(vector<int>& a) {
    vector<int> l(a.size(),-1);
    vector<int> r(a.size(),a.size());
    left(l,a);
    right(r,a);
    long long int ans=0,m=1e9+7;
    for(int i=0;i<a.size();i++){
        ans= (ans + (( (i-l[i])%m * (r[i]-i)%m )%m * a[i])%m)%m;
    }
    return ans;
}
```

Largest Rectangle in Histogram
```
void left(vector<int> &l,vector<int> &h){
    stack<int> s;
    for(int i=0;i<h.size();i++){
        while(!s.empty() && h[i]<=h[s.top()]) s.pop();
        if(!s.empty()) l[i]=s.top();
        s.push(i);
    }
}

void right(vector<int> &r,vector<int> &h){
    stack<int> s;
    for(int i=h.size()-1;i>=0;i--){
        while(!s.empty() && h[i]<=h[s.top()]) s.pop();
        if(!s.empty()) r[i]=s.top();
        s.push(i);
    }
}


int largestRectangleArea(vector<int>& h) {
    vector<int> l(h.size(),-1);
    vector<int> r(h.size(),h.size());
    left(l,h);
    right(r,h);
    int ans=0;
    for(int i=0;i<h.size();i++){
        ans=max(ans,h[i]*(r[i]-l[i]-1));
    }
    return ans;
}
```
Maximal Rectangles
```
int maximalRectangle(vector<vector<char>>& m) {
    int ans=0;
    vector<vector<int>> g(m.size(),vector<int>(m[0].size(),0));
    for(int j=0;j<m[0].size();j++){
        int c=0;
        for(int i=0;i<m.size();i++){
            if(m[i][j]=='1') c++,g[i][j]=c;
            else c=0;
        }
    }
    for(auto it:g){
        ans=max(ans,largestRectangleArea(it));
    }
    return ans;
}
```
Sliding Window Maximum

```
vector<int> maxSlidingWindow(vector<int>& nums, int k) {
    deque<int> dq;
    for(int i=0;i<k;i++){
        while(!dq.empty() && nums[i]>dq.back()) dq.pop_back();
        dq.push_back(nums[i]);
    }
    vector<int> res;
    for(int i=k;i<nums.size();i++){
        res.push_back(dq.front());
        if(dq.front()==nums[i-k]) dq.pop_front();
        while(!dq.empty() && nums[i]>dq.back()) dq.pop_back();
        dq.push_back(nums[i]);
    }
    res.push_back(dq.front());
    return res;
}
```
The Celebrity Problem
```
int celebrity(vector<vector<int> >& m, int n) {
    vector<int> in(n,0);
    vector<int> ou(n,0);
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            if(m[i][j]) ou[i]++,in[j]++;
        }
    }
    for(int i=0;i<n;i++){
        if(!ou[i] && in[i]==n-1) return i;
    }
    return -1;
}
```
LRU Cache
```
class LRUCache {
public:
    class Node{
        public:
            int key;
            int val;
            Node* prev;
            Node* next;

            Node(int key, int val){
                this->key = key;
                this->val = val;
                this->prev = NULL;
                this->next = NULL;
            }
    };

    int cap;
    unordered_map<int,Node*> mp;

    Node* head = new Node(-1,-1);
    Node* tail = new Node(-1,-1);

    LRUCache(int capacity) {
        head->next = tail;
        tail->prev = head;
        cap = capacity;
    }

    void addNode(Node* newnode){
        Node* temp = head->next;
        newnode->next = temp;
        newnode->prev = head;
        head->next = newnode;
        temp->prev = newnode;
    }

    void deleteNode(Node* delnode){
        Node* prv = delnode->prev;
        Node* nxt = delnode->next;
        prv->next = nxt;
        nxt->prev = prv;
    }
    
    int get(int key) {
        if(mp.find(key)!=mp.end()){
            Node* node = mp[key];
            int value = node->val;
            deleteNode(node);
            addNode(node);
            mp[key] = head->next;
            return value;
        }
        return -1;
    }
    
    void put(int key, int value) {
        if(mp.find(key)!=mp.end()){
            Node* node = mp[key];
            mp.erase(key);
            deleteNode(node); 
        }

        if(mp.size() == cap){
            mp.erase(tail->prev->key);
            deleteNode(tail->prev);
        }

        addNode(new Node(key,value));
        mp[key] = head->next;
    }
};
```

# Sliding Window and Two Pointer

Longest Substring Without Repeating Characters
```
int lengthOfLongestSubstring(string s) {
    int f[256]={0};
    int i=0,j=0,n=s.size(),ma=0;
    while(j<n){
        while(j<n && f[s[j]]==0) f[s[j++]]++;
        ma=max(ma,j-i);
        while(i<j && s[i]!=s[j]) f[s[i++]]--;
        f[s[i++]]--;
    }
    return ma;
}
```
Max Consecutive Ones III
```
int longestOnes(vector<int>& a, int k) {
    int n = a.size(),j=0,c=0,ans=0;
    for(int i=0;i<n;i++){
        while(j<n && !(a[j]==0 && c==k)){
            if(a[j]==0) c++;
            j++;
        }
        ans=max(ans,j-i);
        if(a[i]==0) c--;
    }
    return ans;
}
```

Fruits and Baskets
```
int findMaxFruits(vector<int> &a, int n) {
    int l=0,r=0,cnt=0,ans=0;
    int f[10001]={0};
    while(r<n){
        while(r<n && cnt<=2){
            if(f[a[r]]==0) cnt++;
            f[a[r]]++;
            r++;
        }
        ans=max(ans,r-l-1);
        while(l<r && cnt>2){
            f[a[l]]--;
            if(f[a[l]]==0) cnt--;
            l++;
        }
    }
    return ans;
}
```

Longest Repeating Character Replacement
```
int maxFrequentElement(int f[]){
    int ma=0;
    for(int i=0;i<26;i++){
        ma=max(ma,f[i]);
    }
    return ma;
}

int characterReplacement(string s, int k) {
    int l=0,r=0,n=s.size(),ans=0;
    int f[26]={0};
    f[s[0]-'A']++;
    while(r<n){
        while(r<n && r-l+1-maxFrequentElement(f)<=k){
            r++;
            if(r<n) f[s[r]-'A']++;
        }
        ans=max(ans,r-l);
        while(l<r && r-l+1-maxFrequentElement(f)>k){
            f[s[l]-'A']--;
            l++;
        }
    }
    return ans;
}
```

Binary subarray with sum
```
int numSubarraysWithSum(vector<int>& a, int k) {
    int n = a.size(),i=0,j=0,c=0,ans=0,rc,lc;
    if(k==0){
        for(auto it:a){
            if(!it) c++;
            else{
                ans+=((c*(c+1))/2);
                c=0;
            }
        }
        ans+=((c*(c+1))/2);
        return ans;
    }
    while(i<n && j<n){
        rc=0;lc=0;
        while(j<n && !(a[j] && c==k)){
            if(a[j]) c++;
            if(c==k) rc++; 
            j++;
        }
        while(c==k) {
            if(a[i]) c--;
            lc++;
            i++;
        }
        ans+=(rc*lc);
    }
    return ans; 
}
```

Count Number of Nice Subarrays
```
int numberOfSubarrays(vector<int>& a, int k) {
    int n = a.size(),i=0,j=0,c=0,ans=0,rc,lc;
    while(i<n && j<n){
        rc=0;lc=0;
        while(j<n && !(a[j]%2 && c==k)){
            if(a[j]%2) c++;
            if(c==k) rc++; 
            j++;
        }
        while(c==k) {
            if(a[i]%2) c--;
            lc++;
            i++;
        }
        ans+=(rc*lc);
    }
    return ans;
}
```

Number of Substrings Containing All Three Characters
```
int numberOfSubstrings(string s) {
    int mp[3]={0};
    int c=0,ans=0;
    int i=0;
    for(int j=0;j<s.size();j++){
        mp[s[j]-'a']++;
        if(mp[s[j]-'a']==1) c++;
            while(i<s.size() && c==3){
                ans+=(s.size()-j);
                mp[s[i]-'a']--;
                if(mp[s[i]-'a']==0){
                    c--;
                }
                i++;
            }
    }
    return ans;
}
```

Maximum Points You Can Obtain from Cards
```
int maxScore(vector<int>& a, int k) {
    if(k==a.size()) return accumulate(a.begin(),a.end(),0);
    int ans=0,sum=0;
    for(int i=0;i<k;i++){
        sum+=(a[i+a.size()-k]);
    }
    ans=max(ans,sum);
    for(int i=0;i<k;i++){
        sum-=(a[i+a.size()-k]);
        sum+=a[i];
        ans=max(ans,sum);
    }
    return ans;
}
```
Longest Substring with At Most K Distinct Characters
```
int kDistinctChars(int k, string a)
{
    int l=0,r=0,cnt=0,ans=0,n=a.size();
    int f[26]={0};
    while(r<n){
        while(r<n && !(cnt==k && f[a[r]-'a']==0)){
            if(f[a[r]-'a']==0) cnt++;
            f[a[r]-'a']++;
            r++;
        }
        ans=max(ans,r-l);
        while(l<r){
            f[a[l]-'a']--;
            if(f[a[l]-'a']==0) break;
            l++;
        }
        l++;
        cnt--;
    }
    return ans;
}
```
Subarrays with K Different Integers
```
int subarraysAtmostKDistinct(vector<int>& a, int k){
    int l=0,r=0,cnt=0,ans=0,n=a.size();
    int f[20001]={0};
    while(r<n){
        while(r<n){
            if(cnt==k && f[a[r]]==0) break;
            if(f[a[r]]==0) cnt++;
            f[a[r]]++;
            ans+=(r-l+1);
            r++;
        }
        while(l<r){
            if(cnt<k) break;
            f[a[l]]--;
            if(f[a[l]]==0) cnt--;
            l++;
        }
    }
    return ans;
}

int subarraysWithKDistinct(vector<int>& a, int k) {
    int c=subarraysAtmostKDistinct(a,k);
    if(k==1) return c;
    return c-subarraysAtmostKDistinct(a,k-1);
}
```
Minimum Window Substring
```
```
Minimum Window Subsequence
```
```

# Heap

# Greedy

Assign Cookies
```
int findContentChildren(vector<int>& g, vector<int>& s) {
    int i=0,j=0,c=0;
    sort(g.begin(),g.end());
    sort(s.begin(),s.end());
    while(i<g.size() && j<s.size()){
        if(g[i]<=s[j]) i++,j++,c++;
        else j++;
    }
    return c;
}
```

# Binary Tree 

Preorder Traversal
```
void preOrderTrav(node * curr, vector < int > & preOrder) {
  if (curr == NULL) return;
  preOrder.push_back(curr -> data);
  preOrderTrav(curr -> left, preOrder);
  preOrderTrav(curr -> right, preOrder);
}
```
Inorder Traversal
```
void inOrderTrav(node * curr, vector < int > & inOrder) {
  if (curr == NULL) return;
  inOrderTrav(curr -> left, inOrder);
  inOrder.push_back(curr -> data);
  inOrderTrav(curr -> right, inOrder);
}
```

Postorder Traversal
```
void postOrderTrav(node * curr, vector < int > & postOrder) {
  if (curr == NULL) return;
  postOrderTrav(curr -> left, postOrder);
  postOrderTrav(curr -> right, postOrder);
  postOrder.push_back(curr -> data);
}
```
Level Order Traversal
```
vector<int> levelOrder(TreeNode* root) {
    vector<int> ans; 
    if(root == NULL) return ans; 
    queue<TreeNode*> q; 
    q.push(root); 
    while(!q.empty()) {
        TreeNode *temp = q.front(); 
        q.pop(); 
        if(temp->left != NULL) q.push(temp->left); 
        if(temp->right != NULL) q.push(temp->right); 
        ans.push_back(temp->val); 
    }
    return ans; 
}
```
Preorder Traversal (Iterative)
```
vector<int> preOrderTrav(node* curr) {
    vector<int> preOrder;
    if (curr == NULL) return preOrder;
    stack<node*> s;
    s.push(curr);
    while (!s.empty()) {
        node * topNode = s.top();
        preOrder.push_back(topNode -> data);
        s.pop();
        if (topNode -> right != NULL) s.push(topNode -> right);
        if (topNode -> left != NULL) s.push(topNode -> left);
    }
    return preOrder;
}
```
Inorder Traversal (Iterative)
```
vector<int> inOrderTrav(node* curr) {
    vector<int> inOrder;
    stack<node*> s;
    while (true) {
        if (curr != NULL) {
            s.push(curr);
            curr = curr -> left;
        } 
        else {
            if (s.empty()) break;
            curr = s.top();
            inOrder.push_back(curr -> data);
            s.pop();
            curr = curr -> right;
        }
    }
    return inOrder;
}
```
Postorder Traversal (Iterative Two Stacks)
```
vector<int> postOrderTrav(node* curr) {
    vector<int> postOrder;
    if (curr == NULL) return postOrder;
    stack<node*> s1;
    stack<node*> s2;
    s1.push(curr);
    while (!s1.empty()) {
        curr = s1.top();
        s1.pop();
        s2.push(curr);
        if (curr -> left != NULL) s1.push(curr -> left);
        if (curr -> right != NULL) s1.push(curr -> right);
    }
    while (!s2.empty()) {
        postOrder.push_back(s2.top() -> data);
        s2.pop();
    }
    return postOrder;
}
```
Postorder Traversal (Iterative Single Stack)
```
vector<int> postOrderTrav(node* cur) {
    vector<int> postOrder;
    if (cur == NULL) return postOrder;
    stack<node*> st;
    while (cur != NULL || !st.empty()) {
        if (cur != NULL) {
            st.push(cur);
            cur = cur -> left;
        } 
        else {
            node * temp = st.top() -> right;
            if (temp == NULL) {
                temp = st.top();
                st.pop();
                postOrder.push_back(temp -> data);
                while (!st.empty() && temp == st.top() -> right) {
                    temp = st.top();
                    st.pop();
                    postOrder.push_back(temp -> data);
                }
            } 
            else cur = temp;
        }
    }
    return postOrder;
}
```
All Traversals in One
```
void allTraversal(node* root, vector<int> &pre, vector<int> &in , vector<int> &post) {
    stack<pair<node*,int>> st;
    st.push({root,1});
    if (root == NULL) return;
    while (!st.empty()) {
        auto it = st.top();
        st.pop();
        if (it.second == 1) {
            pre.push_back(it.first -> data);
            it.second++;
            st.push(it);
            if (it.first -> left != NULL) st.push({it.first -> left,1});
        }
        else if (it.second == 2) {
            in .push_back(it.first -> data);
            it.second++;
            st.push(it);
            if (it.first -> right != NULL) st.push({it.first -> right,1});
        }
        else {
            post.push_back(it.first -> data);
        }
    }
}
```
Maximum Depth of Binary Tree
```
int maxDepth(TreeNode* root) {
    if(!root) return 0;
    return 1+max(maxDepth(root->left),maxDepth(root->right));
}
```
Balanced Binary Tree
```
int f(TreeNode* root){
    if(!root) return 0;
    int l=f(root->left);
    if(l==-1) return -1;
    int r=f(root->right);
    if(r==-1) return -1;
    if(abs(l-r)>1) return -1;
    return 1+max(l,r);
}
bool isBalanced(TreeNode* root) {
    return f(root)!=-1;
}
```
Diameter of Binary Tree
```
int f(TreeNode* root,int &ans){
    if(!root) return 0;
    int l=f(root->left,ans);
    int r=f(root->right,ans);
    ans=max(ans,l+r);
    return 1+max(l,r);
}

int diameterOfBinaryTree(TreeNode* root) {
    int ans=0;
    f(root,ans);
    return ans;
}
```
Maximum Path Sum
```
int f(TreeNode* root,int &ans){
    if(!root) return INT_MIN;
    int l=f(root->left,ans);
    if(l<0) l=0;
    int r=f(root->right,ans);
    if(r<0) r=0;
    ans=max(ans,root->val+l+r);
    return root->val+max(l,r);
}
    
int maxPathSum(TreeNode* root) {
    int ans=INT_MIN;
    f(root,ans);
    return ans;
}
```
Trees are identical or not 
```
bool f(TreeNode* p, TreeNode* q){
    if(!p && !q) return true;
    if(!p || !q) return false;
    if(p->val!=q->val) return false;
    return f(p->left,q->left) && f(p->right,q->right);
}

bool isSameTree(TreeNode* p, TreeNode* q) {
    return f(p,q);
}
```
Zigzag Level Order Traversal
```
vector<vector<int>> zigzagLevelOrder(TreeNode* root) {
    queue<TreeNode*> q;
    q.push(root);
    vector<vector<int>> res;
    if(!root) return res;
    int flag=0;
    while(!q.empty()){
        int sz=q.size();
        vector<int> level;
        while(sz--){
            TreeNode* x=q.front();
            q.pop();
            level.push_back(x->val);
            if(x->left) q.push(x->left);
            if(x->right) q.push(x->right);
        }
        if(flag) reverse(level.begin(),level.end());
        flag=~flag;
        res.push_back(level);
    }
    return res;
}
```
Boundary Traversal
```
bool isLeaf(node * root) {
    return !root -> left && !root -> right;
}

void addLeftBoundary(node * root, vector < int > & res) {
    node * cur = root -> left;
    while (cur) {
        if (!isLeaf(cur)) res.push_back(cur -> data);
        if (cur -> left) cur = cur -> left;
        else cur = cur -> right;
    }
}

void addRightBoundary(node * root, vector < int > & res) {
    node * cur = root -> right;
    vector < int > tmp;
    while (cur) {
        if (!isLeaf(cur)) tmp.push_back(cur -> data);
        if (cur -> right) cur = cur -> right;
        else cur = cur -> left;
    }
    for (int i = tmp.size() - 1; i >= 0; --i) {
        res.push_back(tmp[i]);
    }
}

void addLeaves(node * root, vector < int > & res) {
    if (isLeaf(root)) {
        res.push_back(root -> data);
        return;
    }
    if (root -> left) addLeaves(root -> left, res);
    if (root -> right) addLeaves(root -> right, res);
}

vector<int> printBoundary(node* root) {
    vector<int> res;
    if (!root) return res;
    if (!isLeaf(root)) res.push_back(root -> data);
    addLeftBoundary(root, res);
    addLeaves(root, res);
    addRightBoundary(root, res);
    return res;
}
```
Vertical Order Traversal
```
vector<vector<int>> verticalTraversal(TreeNode* root) {
    queue<pair<TreeNode*,pair<int,int>>> q;
    q.push({root,{0,0}});
    map<int,map<int,multiset<int>>> mp;
    int x,y;
    while(!q.empty()){
        TreeNode* node =q.front().first;
        x=q.front().second.first;
        y=q.front().second.second;
        q.pop();
        mp[x][y].insert(node->val);
        if(node->left){
            q.push({node->left,{x-1,y+1}});
        }
        if(node->right){
            q.push({node->right,{x+1,y+1}});
        }
    }
    vector<vector<int>> ans;
    for(auto i:mp){
        vector<int> level;
        for(auto j:i.second){
            level.insert(level.end(), j.second.begin(), j.second.end());
        }
        ans.push_back(level);
    }
    return ans;
}
```
Top View
```
vector<int> topView(Node *root) {
    map<int,int> mp;
    vector <int> res;
    if(!root) return res;
    queue<pair<Node *,int>> q;
    q.push({root,0});
    while(!q.empty()){
        Node *x=q.front().first;
        int h=q.front().second;
        if(mp.find(h)==mp.end()) mp[h]=x->data;
        q.pop();
        if(x->left) q.push({x->left,h-1});
        if(x->right) q.push({x->right,h+1});
    }
    for(auto it:mp) res.push_back(it.second);
    return res;
}
```
Bottom View
```
vector <int> bottomView(Node *root) {
    vector <int> res;
    if(!root) return res;
    map<int,int> mp;
    queue<pair<Node *,int>> q;
    q.push({root,0});
    while(!q.empty()){
        Node *x=q.front().first;
        int h=q.front().second;
        mp[h]=x->data;
        q.pop();
        if(x->left) q.push({x->left,h-1});
        if(x->right) q.push({x->right,h+1});
    }
    for(auto it:mp) res.push_back(it.second);
    return res;
}
```
Left View
```
vector<int> rightSideView(TreeNode* root) {
    vector<int> res;
    if(!root) return res;
    queue<TreeNode *> q;
    q.push(root);
    while(!q.empty()){
        res.push_back(q.front()->val);
        int sz=q.size();
        while(sz--){
            TreeNode* x=q.front();
            q.pop();
            if(x->left) q.push(x->left);
            if(x->right) q.push(x->right);
        } 
    }
    return res;
}
```
Right View
```
vector<int> rightSideView(TreeNode* root) {
    vector<int> res;
    if(!root) return res;
    queue<TreeNode *> q;
    q.push(root);
    while(!q.empty()){
        res.push_back(q.front()->val);
        int sz=q.size();
        while(sz--){
            TreeNode* x=q.front();
            q.pop();
            if(x->right) q.push(x->right);
            if(x->left) q.push(x->left);
        } 
    }
    return res;
}
```
Symmetric Binary Tree
```
bool f(TreeNode* p,TreeNode* q){
    if(!p && !q) return true;
    if(!p || !q) return false;
    if(p->val!=q->val) return false;
    bool l=f(p->left,q->right);
    bool r=f(p->right,q->left);
    return l && r;
}

bool isSymmetric(TreeNode* root) {
    return f(root,root);
}
```
Print Root to Node Path
```
bool getPath(node * root, vector < int > & arr, int x) {
    if (!root) return false;
    arr.push_back(root -> data);
    if (root -> data == x) return true;
    if (getPath(root -> left, arr, x) || getPath(root -> right, arr, x)) return true; 
    arr.pop_back();
    return false;
}
```
Lowest Common Ancestor
```
TreeNode* f(TreeNode* root, TreeNode* p, TreeNode* q){
    if(!root) return NULL;
    if(root==p || root==q) return root;
    TreeNode* l=f(root->left,p,q);
    TreeNode* r=f(root->right,p,q);
    if(l && r) return root;
    return l?l:r;
}

TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
    return f(root,p,q);
}
```
Maximum Width
```
```
Children Sum Property
```
bool isParentSum(Node *root){
    if(!root || (!root->left && !root->right)) return true;
    int l=0,r=0;
    if(root->left) l=root->left->data;
    if(root->right) r=root->right->data;
    if(root->data != l+r) return false;
    if(!isParentSum(root->left)) return false;
    if(!isParentSum(root->right)) return false;
    return true;
}
```
All Nodes Distance K
```
```
Minimum time taken to BURN
```
```
Count Nodes in Complete Binary Tree
```
```
Construct Binary Tree from Inorder and Preorder
```
```
Construct Binary Tree from Inorder and PostOrder
```
```
Serialize And Deserialize a Binary Tree
```
```
Flatten Binary Tree to LinkedList
```
void f(TreeNode* root,TreeNode* &prev){
    if(!root) return;
    if(prev){
        prev->right=root;
        prev->left=NULL;
    }
    prev=root;
    f(root->left,prev);
    f(root->right,prev);
}

void flatten(TreeNode* root) {
    TreeNode *prev=NULL;
    f(root,prev);
}
```


# Binary Search Tree

Search
```
TreeNode* searchBST(TreeNode* root, int t) {
    if(!root) return NULL;
    TreeNode* l;
    if(root->val==t) return root;
    else if(root->val<t) l=searchBST(root->right,t);
    else if(root->val>t) l=searchBST(root->left,t);
    return l;
}
```
Ceil 
```
int findCeil(node *root, int input) {
    int ceil = -1;
    while (root) {
        if (root->data == input) return input;
        else if (root->data < input) root = root->right;
        else {
            ceil = root->data;
            root = root->left;
        }
    }
    return ceil;
}
```
Floor 
```
int findFloor(node *root, int input) {
    int floor = -1;
    while (root) {
        if (root->data == input) return input;
        else if (root->data < input)
        {
            floor = root->data;
            root = root->right;
        }
        else root = root->left;
    }
    return floor;
}
```
Insert 
```
TreeNode* insertIntoBST(TreeNode* root, int val) {
    TreeNode* node=new TreeNode(val);
    if(!root) return node;
    TreeNode *temp=root, *prev=NULL;
    while(temp){
        prev=temp;
        if(temp->val<val) temp=temp->right;
        else temp=temp->left;
    }
    if(prev->val<val) prev->right=node;
    else prev->left=node;
    return root;
}
```
Delete 
```
```
K-th Smallest
```
void f(TreeNode* root,int &k,int &ans){
    if(!root) return;
    f(root->left,k,ans);
    k--;
    if(k==0){
        ans=root->val;
        return;
    }
    f(root->right,k,ans);
}

int kthSmallest(TreeNode* root, int k) {
    int ans=0;
    f(root,k,ans);
    return ans;
}
```
K-th Largest
```
void f(TreeNode* root,int &k,int &ans){
    if(!root) return;
    f(root->right,k,ans);
    k--;
    if(k==0){
        ans=root->val;
        return;
    }
    f(root->left,k,ans);
}

int kthSmallest(TreeNode* root, int k) {
    int ans=0;
    f(root,k,ans);
    return ans;
}
```
Validate BST
```
bool f(TreeNode* root,TreeNode* &prev){
    if(!root) return true;
    if(!f(root->left,prev)) return false;
    if(prev) if(prev->val>=root->val) return false;
    prev=root;
    if(!f(root->right,prev)) return false;
    return true;
}

bool isValidBST(TreeNode* root) {
    TreeNode* prev=NULL;
    return f(root,prev);
}
```
LCA 
```
TreeNode* lca(TreeNode* root, TreeNode* p, TreeNode* q){
    if(root->val == p->val || root->val == q->val) return root;
    else if((root->val > p->val && root->val < q->val) || (root->val < p->val && root->val > q->val)) return root;
    else if(root->val < p->val && root->val < q->val) return lca(root->right,p,q);
    else return lca(root->left,p,q);
}
```
Construct BST from Preorder Traversal
```
```
Inorder Successor in BST
```
```
Inorder Predecessor in BST
```
```
Merge 2 BST's
```
```
Two Sum In BST
```
```
Recover BST
```
```
Largest BST in Binary Tree
```
```


# Graph

BFS
```
vector<int>bfsOfGraph(int V, vector<int> adj[]){
    vector<int> bfs; 
    vector<int> vis(V, 0); 
    queue<int> q; 
    q.push(0); 
    vis[0] = 1; 
    while(!q.empty()) {
        int node = q.front();
        q.pop(); 
        bfs.push_back(node); 
        for(auto it : adj[node]) {
            if(!vis[it]) {
                q.push(it); 
                vis[it] = 1; 
            }
        }
    }
    return bfs; 
}
```
DFS
```
void dfs(int node, vector<int> &vis, vector<int> adj[], vector<int> &storeDfs) {
    storeDfs.push_back(node); 
    vis[node] = 1; 
    for(auto it : adj[node]) {
        if(!vis[it]) {
            dfs(it, vis, adj, storeDfs); 
        }
    }
}

vector<int>dfsOfGraph(int V, vector<int> adj[]){
    vector<int> storeDfs; 
    vector<int> vis(V+1, 0); 
    for(int i = 1;i<=V;i++) {
        if(!vis[i]) dfs(i, vis, adj, storeDfs); 
    }
    return storeDfs; 
}
```
Number of Provinces
```
void f(int node,int n,vector<vector<int>>& g,vector<bool> &vis){
    vis[node]=true;
    for(int i=0;i<n;i++){
        if(g[node][i]==1 && !vis[i]){
            f(i,n,g,vis);
        }
    }
}

int findCircleNum(vector<vector<int>>& g) {
    int n=g.size(),count=0;
    vector<bool> vis(n,false);
    for(int i=0;i<n;i++){
        if(!vis[i]){
            f(i,n,g,vis);
            count++;
        }
    }
    return count;
}
```
Connected Components in Matrix
```
```
Rotting Oranges
```
int orangesRotting(vector<vector<int>>& grid) {
    queue<pair<int,int>> q;
    int tot=0,cnt=0,ans=0;
    for(int i=0;i<grid.size();i++){
        for(int j=0;j<grid[0].size();j++){
            if(grid[i][j]!=0) tot++;
            if(grid[i][j]==2) q.push({i,j});
        }
    }
    int dx[]={0,0,1,-1};
    int dy[]={1,-1,0,0};
    while(!q.empty()){
        int sz=q.size();
        cnt+=sz;
        while(sz--){
            int x=q.front().first;
            int y=q.front().second;
            q.pop();
            for(int i=0;i<4;i++){
                int nx=x+dx[i];
                int ny=y+dy[i];
                if(nx>=0 && ny>=0 && nx<grid.size() && ny<grid[0].size() && grid[nx][ny]==1){
                    grid[nx][ny]=2;
                    q.push({nx,ny});
                } 
            }
        }
        if(!q.empty()) ans++;
    }
    if(tot==cnt) return ans;
    else return -1;
}
```
Flood fill
```
void dfs(vector<vector<int>>& m, int i, int j,int p, int n){
    if(i>=0 && i<m.size() && j>=0 && j<m[0].size() && m[i][j]==p){
        m[i][j]=n;
        int x[4]={0,0,1,-1};
        int y[4]={1,-1,0,0};
        for(int k=0;k<4;k++) dfs(m,i+x[k],j+y[k],p,n);
    }
    return;
}

vector<vector<int>> floodFill(vector<vector<int>>& m, int i, int j, int new_color) {
    int prev_color=m[i][j];
    if(prev_color == new_color) return m;
    dfs(m,i,j,prev_color,new_color);
    return m;
}
```
Cycle check Undirected Graph BFS
```
bool checkForCycle(int s, int V, vector<int> adj[], vector<int>& visited)
{
    vector<int> parent(V, -1);
    queue<pair<int,int>> q;
    visited[s] = true;
    q.push({s, -1});
    while (!q.empty()) {
        int node = q.front().first;
        int par = q.front().second;
        q.pop();
        for (auto it : adj[node]) {
            if (!visited[it]) {
                visited[it] = true;
                q.push({it, node});
            }
            else if (par != it)
                return true;
        }
    }
    return false;
}

bool isCycle(int V, vector<int>adj[]){
    vector<int> vis(V, 0); 
    for(int i = 0;i<V;i++) {
        if(!vis[i]) {
            if(checkForCycle(i, V, adj, vis)) return true; 
        }
    }
    return false; 
}
```
Cycle check Undirected Graph DFS
```
bool checkForCycle(int node, int parent, vector<int> &vis, vector<int> adj[]) {
    vis[node] = 1; 
    for(auto it: adj[node]) {
        if(!vis[it]) {
            if(checkForCycle(it, node, vis, adj)) 
                return true; 
        }
        else if(it!=parent) 
            return true; 
    }
    return false; 
}

bool isCycle(int V, vector<int>adj[]){
    vector<int> vis(V+1, 0); 
    for(int i = 0;i<V;i++) {
        if(!vis[i]) {
            if(checkForCycle(i, -1, vis, adj)) return true; 
        }
    }
    return false; 
}
```
Cycle check Directed Graph BFS
```
bool isCyclic(int N, vector<int> adj[]) {
    queue<int> q; 
    vector<int> indegree(N, 0); 
    for(int i = 0;i<N;i++) {
        for(auto it: adj[i]) {
            indegree[it]++; 
        }
    }
    for(int i = 0;i<N;i++) {
        if(indegree[i] == 0) {
            q.push(i); 
        }
    }
    int cnt = 0;
    while(!q.empty()) {
        int node = q.front(); 
        q.pop(); 
        cnt++; 
        for(auto it : adj[node]) {
            indegree[it]--;
            if(indegree[it] == 0) {
                q.push(it); 
            }
        }
    }
    if(cnt == N) return false; 
    return true; 
}
```
Cycle check Directed Graph DFS
```
bool checkCycle(int node, vector<int> adj[], int vis[], int dfsVis[]) {
    vis[node] = 1; 
    dfsVis[node] = 1; 
    for(auto it : adj[node]) {
        if(!vis[it]) {
            if(checkCycle(it, adj, vis, dfsVis)) return true;
        } else if(dfsVis[it]) {
            return true; 
        }
    }
    dfsVis[node] = 0; 
    return false;
}

bool isCyclic(int N, vector<int> adj[]) {
    int vis[N], dfsVis[N]; 
    memset(vis, 0, sizeof vis); 
    memset(dfsVis, 0, sizeof dfsVis); 
    for(int i = 0;i<N;i++) {
        if(!vis[i]) {
            if(checkCycle(i, adj, vis, dfsVis)) {
                return true; 
            }
        }
    }
    return false; 
}
```
0/1 Matrix
```
```
Surrounded Regions
```
void f(int i,int j,vector<vector<char>>& board,int r,int c){
    if(i<0 || i>=r || j<0 || j>=c || board[i][j]!='O'){
        return;
    }
    if(board[i][j]=='O') board[i][j]='#';
    f(i+1,j,board,r,c);
    f(i-1,j,board,r,c);
    f(i,j+1,board,r,c);
    f(i,j-1,board,r,c);
}

void solve(vector<vector<char>>& board) {
    int r=board.size();
    int c=board[0].size();
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            if((i==0 || i==r-1 || j==0 || j==c-1) &&  board[i][j]=='O'){
                f(i,j,board,r,c);
            }
        }
    }
        for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            if(board[i][j]=='#') board[i][j]='O';
            else board[i][j]='X';
        }
    }   
}
```
Number of Enclaves
```
void dfs(vector<vector<int>>& m,int i,int j){
    if(i>=0 && i<m.size() && j>=0 && j<m[0].size() && m[i][j]==1){
        m[i][j]=0;
        int x[4]={0,0,1,-1};
        int y[4]={1,-1,0,0};
        for(int k=0;k<4;k++) dfs(m,i+x[k],j+y[k]);
    }
}

int numEnclaves(vector<vector<int>>& m) {
    int r=m.size(),c=m[0].size(),count=0;
    for(int i=0;i<r;i++) for(int j=0;j<c;j++) if((i==0 || i==r-1 || j==0 || j==c-1) && m[i][j]==1) dfs(m,i,j);
    for(int i=0;i<r;i++) for(int j=0;j<c;j++) if(m[i][j]) count++;
    return count; 
}
```
Word Ladder 1
```
int ladderLength(string s, string t, vector<string>& a) {
    unordered_map<string,bool> mp;
    for(int i=0;i<a.size();i++) mp[a[i]]=false; 
    queue<string> q;
    string temp;
    int step=1;
    q.push(s);
    while(!q.empty()){
        int sz=q.size();
        while(sz--){
            string x=q.front();
            if(x==t) return step;
            q.pop();
            for(int i=0;i<x.size();i++){
                for(char j='a';j<='z';j++){
                    temp=x;
                    temp[i]=j;
                    if(mp.find(temp)!=mp.end() && !mp[temp]){
                        mp[temp]=true;
                        q.push(temp);
                    }
                }
            }
        }
        step++;
    }
    return 0;
}
```
Word Ladder 2
```
```
Number of Islands 2
```
void bfs(int row, int col, vector<vector<int>> &vis, vector<vector<char>>&grid) {
    vis[row][col] = 1; 
    queue<pair<int,int>> q;
    q.push({row, col}); 
    int n = grid.size(); 
    int m = grid[0].size(); 
    while(!q.empty()) {
        int row = q.front().first; 
        int col = q.front().second; 
        q.pop(); 
        for(int delrow = -1; delrow<=1;delrow++) {
            for(int delcol = -1; delcol <= 1; delcol++) {
                int nrow = row + delrow; 
                int ncol = col + delcol; 
                if(nrow >= 0 && nrow < n && ncol >= 0 && ncol < m 
                && grid[nrow][ncol] == '1' && !vis[nrow][ncol]) {
                    vis[nrow][ncol] = 1; 
                    q.push({nrow, ncol}); 
                }
            }
        }
    }
}

int numIslands(vector<vector<char>>& grid) {
    int n = grid.size(); 
    int m = grid[0].size(); 
    vector<vector<int>> vis(n, vector<int>(m, 0)); 
    int cnt = 0; 
    for(int row = 0; row < n ; row++) {
        for(int col = 0; col < m ;col++) {
            if(!vis[row][col] && grid[row][col] == '1') {
                cnt++; 
                bfs(row, col, vis, grid); 
            }
        }
    }
    return cnt; 
}
```
Bipartite Graph
```
bool isBipartite(vector<vector<int>>& g) {
    vector<int> vis(g.size(),-1);
    queue<int> q;
    for(int i=0;i<g.size();i++){
        if(vis[i]!=-1) continue;
        q.push(i);
        vis[i]=0;
        int node;
        while(!q.empty()){
            node=q.front();
            q.pop();
            for(auto it:g[node]){
                if(vis[it]==-1){
                    vis[it]=1-vis[node];
                    q.push(it);
                }
                else if(vis[it]==vis[node]) return false;
            }
        }
    }
    return true;
}
```
Kahn’s Algorithm (Topological Sort)
```
vector<int> topoSort(int V, vector<int> adj[])
{
    int indegree[V] = {0};
    for (int i = 0; i < V; i++) {
        for (auto it : adj[i]) {
            indegree[it]++;
        }
    }
    queue<int> q;
    for (int i = 0; i < V; i++) {
        if (indegree[i] == 0) {
            q.push(i);
        }
    }
    vector<int> topo;
    while (!q.empty()) {
        int node = q.front();
        q.pop();
        topo.push_back(node);
        for (auto it : adj[node]) {
            indegree[it]--;
            if (indegree[it] == 0) q.push(it);
        }
    }
    return topo;
}
```
Course Schedule 1
```
bool canFinish(int numCourses, vector<vector<int>>& prerequisites) {
    vector<int> g[numCourses];
    vector<int> in(numCourses,0);
    for(int i=0;i<prerequisites.size();i++){
        g[prerequisites[i][1]].push_back(prerequisites[i][0]);
        in[prerequisites[i][0]]++;
    }
    int count=0;
    queue<int> q;
    for(int i=0;i<numCourses;i++) if(in[i]==0) q.push(i);
    while(!q.empty()){
        int x=q.front();
        q.pop();
        count++;
        for(auto it:g[x]){
            in[it]--;
            if(in[it]==0) q.push(it); 
        }
    }
    if(count==numCourses) return true;
    return false;
}
```
Course Schedule 2
```
vector<int> findOrder(int numCourses, vector<vector<int>>& prerequisites) {
    vector<int> ans;
    vector<int> g[numCourses];
    vector<int> in(numCourses,0);
    for(int i=0;i<prerequisites.size();i++){
        g[prerequisites[i][1]].push_back(prerequisites[i][0]);
        in[prerequisites[i][0]]++;
    }
    int count=0;
    queue<int> q;
    for(int i=0;i<numCourses;i++) if(in[i]==0) q.push(i);
    while(!q.empty()){
        int x=q.front();
        ans.push_back(x);
        q.pop();
        count++;
        for(auto it:g[x]){
            in[it]--;
            if(in[it]==0) q.push(it); 
        }
    }
    if(count==numCourses) return ans;
    return {};
}
```
Find Eventual Safe States
```
vector<int> eventualSafeNodes(vector<vector<int>>& l) {
    vector<vector<int>> g(l.size());
    for(int i=0;i<l.size();i++) for(int j=0;j<l[i].size();j++) g[l[i][j]].push_back(i);
    vector<int> in(g.size(),0);
    vector<int> a;
    for(int i=0;i<g.size();i++) for(int j=0;j<g[i].size();j++) in[g[i][j]]++;
    queue<int> q;
    for(int i=0;i<in.size();i++) if(!in[i]) q.push(i);
    while(!q.empty()){
        int x=q.front();
        a.push_back(x);
        q.pop();
        for(auto it:g[x]){
            in[it]--;
            if(!in[it]) q.push(it);
        }
    } 
    sort(a.begin(),a.end());
    return a;
}
```
Alien dictionary
```
```
Shortest Path in Undirected Graph with Unit distance
```
vector<int> shortestPath(vector<vector<int>>& edges, int N,int M, int src){
    vector<int> adj[N]; 
    for(auto it : edges) {
        adj[it[0]].push_back(it[1]); 
        adj[it[1]].push_back(it[0]); 
    }
    int dist[N];
    for(int i = 0;i<N;i++) dist[i] = 1e9;
    dist[src] = 0; 
    queue<int> q;
    q.push(src); 
    while(!q.empty()) {
        int node = q.front(); 
        q.pop(); 
        for(auto it : adj[node]) {
            if(dist[node] + 1 < dist[it]) {
                dist[it] = 1 + dist[node]; 
                q.push(it); 
            }
        }
    }
    return dist; 
}
```
Shortest Path in DAG
```
void topoSort(int node, vector < pair < int, int >> adj[],
    int vis[], stack < int > & st) {
    vis[node] = 1;
    for (auto it: adj[node]) {
        int v = it.first;
        if (!vis[v]) topoSort(v, adj, vis, st);
    }
    st.push(node);
}

vector < int > shortestPath(int N, int M, vector < vector < int >> & edges) {
    vector < pair < int, int >> adj[N];
    for (int i = 0; i < M; i++) {
        int u = edges[i][0];
        int v = edges[i][1];
        int wt = edges[i][2];
        adj[u].push_back({v, wt}); 
    }
    int vis[N] = {0};
    stack < int > st;
    for (int i = 0; i < N; i++) {
        if (!vis[i]) topoSort(i, adj, vis, st);
    }
    vector < int > dist(N);
    for (int i = 0; i < N; i++) dist[i] = 1e9;
    dist[0] = 0;
    while (!st.empty()) {
        int node = st.top();
        st.pop();
        for (auto it: adj[node]) {
            int v = it.first;
            int wt = it.second;
            if (dist[node] + wt < dist[v]) {
                dist[v] = wt + dist[node];
            }
        }
    }
    return dist;
}
```
Dijkstra Algorithm
```
vector <int> dijkstra(int V, vector<vector<int>> adj[], int S) {
    set<pair<int,int>> st; 
    vector<int> dist(V, 1e9); 
    st.insert({0, S}); 
    dist[S] = 0;
    while(!st.empty()) {
        auto it = *(st.begin()); 
        int node = it.second; 
        int dis = it.first; 
        st.erase(it); 
        for(auto it : adj[node]) {
            int adjNode = it[0]; 
            int edgW = it[1]; 
            if(dis + edgW < dist[adjNode]) {
                if(dist[adjNode] != 1e9) st.erase({dist[adjNode], adjNode}); 
                dist[adjNode] = dis + edgW; 
                st.insert({dist[adjNode], adjNode}); 
                }
        }
    }
    return dist; 
}
```
Dijkstra Algorithm (Efficient)
```
vector<int> dijkstra(int V, vector<vector<int>> adj[], int S) { 
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    vector<int> distTo(V, INT_MAX);
    distTo[S] = 0;
    pq.push({0, S});
    while (!pq.empty())
    {
        int node = pq.top().second;
        int dis = pq.top().first;
        pq.pop();
        for (auto it : adj[node])
        {
            int v = it[0];
            int w = it[1];
            if (dis + w < distTo[v])
            {
                distTo[v] = dis + w;
                pq.push({dis + w, v});
            }
        }
    }
    return distTo;
}
```
Shortest Path in Binary Matrix
```
int shortestPathBinaryMatrix(vector<vector<int>>& g) {
    if(g[0][0]==1) return -1;
    queue<pair<int,int>> q;
    q.push({0,0});
    int c=0;
    int x_arr[]={-1,0,1,-1,1,-1,0,1};
    int y_arr[]={-1,-1,-1,0,0,1,1,1};
    int x,y,nx,ny;
    while(!q.empty()){
        c++;
        int sz=q.size();
        while(sz--){
            x=q.front().first;
            y=q.front().second;
            if(x==g.size()-1 && y==g.size()-1) return c;
            q.pop();
            for(int i=0;i<8;i++){
                nx=x+x_arr[i];
                ny=y+y_arr[i];
                if(nx>=0 && nx<g.size() && nx>=0 && ny<g.size() && !g[nx][ny]){
                    g[nx][ny]=1;
                    q.push({nx,ny});
                }
            }
        }
    }
    return -1;
}
```
Path With Minimum Effort
```
int minimumEffortPath(vector<vector<int>>& g) {
    int r=g.size(),c=g[0].size();
    priority_queue<pair<int,pair<int,int>>,vector<pair<int,pair<int,int>>>,greater<pair<int,pair<int,int>>>> pq;
    pq.push({0,{0,0}});
    vector<vector<int>> dist(r,vector<int>(c,1e9));
    dist[0][0]=0;
    int x_arr[]={0,0,1,-1};
    int y_arr[]={1,-1,0,0};
    int nx,ny,diff,x,y,ma;
    while(!pq.empty()){
        auto p=pq.top();
        pq.pop();
        diff=p.first;
        x=p.second.first;
        y=p.second.second;
        if(x==r-1 && y==c-1) return diff;
        for(int i=0;i<4;i++){
            nx=x+x_arr[i];
            ny=y+y_arr[i];
            if(nx>=0 && nx<r && ny>=0 && ny<c){
                ma=max(diff,abs(g[x][y]-g[nx][ny]));
                if(ma<dist[nx][ny]){
                    dist[nx][ny]=ma;
                    pq.push({ma,{nx,ny}});
                }
            }
        }
    }
    return 0;
}
```
Cheapest Flights Within K Stops
```
int findCheapestPrice(int n, vector<vector<int>>& e, int s, int t, int k) {
    vector<pair<int,int>> g[n];
    for(auto it:e) g[it[0]].push_back({it[1],it[2]});
    queue<pair<int,pair<int,int>>> q;
    vector<int> dist(n,1e9);
    q.push({0,{s,0}});
    dist[s]=0;
    int step,node,weight;
    while(!q.empty()){
        auto p=q.front();
        q.pop();
        step=p.first;
        node=p.second.first;
        weight=p.second.second;
        for(auto it:g[node]){
            if(dist[it.first]>it.second+weight && step<=k){
                dist[it.first]=it.second+weight;
                q.push({step+1,{it.first,dist[it.first]}});
            }
        }
    }
    if(dist[t]==1e9) return -1;
    return dist[t];
}
```
Network Delay Time
```
int networkDelayTime(vector<vector<int>>& times, int n, int k) {
    vector<pair<int,int>> g[n];
    for(int i=0;i<times.size();i++){
        g[times[i][0]-1].push_back({times[i][1]-1,times[i][2]});            
    }
    vector<int> dist(n,1e9);
    dist[k-1]=0;
    priority_queue<pair<int,int>,vector<pair<int,int>>,greater<pair<int,int>>> q;
    q.push({0,k-1});
    while(!q.empty()){
        int d=q.top().first;
        int x=q.top().second;
        q.pop();
        for(auto it:g[x]){
            if(dist[it.first]>dist[x]+it.second){
                dist[it.first]=dist[x]+it.second;
                q.push({dist[it.first],it.first});
            }
        }
    }
    int ans=INT_MIN;
    for(int i=0;i<n;i++){
        ans=max(ans,dist[i]);
    }
    if(ans==1e9) return -1;
    return ans;
}
```
Number of Ways to Arrive at Destination
```
```
Minimum Multiplications to Reach End
```
int minimumMultiplications(vector<int> &arr, int start, int end) {
    queue<pair<int, int>> q;
    q.push({start, 0});
    vector<int> dist(100000, 1e9);
    dist[start] = 0;
    int mod = 100000;
    while (!q.empty())
    {
        int node = q.front().first;
        int steps = q.front().second;
        q.pop();
        for (auto it : arr)
        {
            int num = (it * node) % mod;
            if (steps + 1 < dist[num])
            {
                dist[num] = steps + 1;
                if (num == end)
                    return steps + 1;
                q.push({num, steps + 1});
            }
        }
    }
    return -1;
}
```
Bellman Ford Algorithm
```
vector<int> bellman_ford(int V, vector<vector<int>>& edges, int S) {
    vector<int> dist(V, 1e8);
    dist[S] = 0;
    for (int i = 0; i < V - 1; i++) {
        for (auto it : edges) {
            int u = it[0];
            int v = it[1];
            int wt = it[2];
            if (dist[u] != 1e8 && dist[u] + wt < dist[v]) {
                dist[v] = dist[u] + wt;
            }
        }
    }
    for (auto it : edges) {
        int u = it[0];
        int v = it[1];
        int wt = it[2];
        if (dist[u] != 1e8 && dist[u] + wt < dist[v]) {
            return { -1};
        }
    }
    return dist;
}
```
Floyd Warshall Algorithm
```
void shortest_distance(vector<vector<int>>&matrix) {
    int n = matrix.size();
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if (matrix[i][j] == -1) matrix[i][j] = 1e9;
            if (i == j) matrix[i][j] = 0;
        }
    }
    for (int k = 0; k < n; k++) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                matrix[i][j] = min(matrix[i][j], matrix[i][k] + matrix[k][j]);
            }
        }
    }
}
```
Find the City With the Smallest Number of Neighbors at a Threshold Distance
```
    int findTheCity(int n, vector<vector<int>>& e, int t) {
        vector<vector<int>> g(n,vector<int>(n,INT_MAX));
        for(auto it:e){
            g[it[0]][it[1]]=it[2];
            g[it[1]][it[0]]=it[2];
        }
        for(int i=0;i<n;i++) g[i][i]=0;
        for(int k=0;k<n;k++){
            for(int i=0;i<n;i++){
                for(int j=0;j<n;j++){
                    if(g[i][k]!=INT_MAX && g[k][j]!=INT_MAX) g[i][j]=min(g[i][j],g[i][k]+g[k][j]);
                }
            }
        }
        int c,city=-1,v=n;
        for(int i=0;i<n;i++){
            c=0;
            for(auto j:g[i]){
                if(j<=t) c++;
            }
            if(c<=v){
                v=c;
                city=i;
            }
        }
        return city;
    }
```
Prim’s Algorithm
```
```
Disjoint Set Union
```
public:
    DisjointSet(int n) {
        rank.resize(n + 1, 0);
        parent.resize(n + 1);
        size.resize(n + 1);
        for (int i = 0; i <= n; i++) {
            parent[i] = i;
            size[i] = 1;
        }
    }

    int findUPar(int node) {
        if (node == parent[node])
            return node;
        return parent[node] = findUPar(parent[node]);
    }

    void unionByRank(int u, int v) {
        int ulp_u = findUPar(u);
        int ulp_v = findUPar(v);
        if (ulp_u == ulp_v) return;
        if (rank[ulp_u] < rank[ulp_v]) {
            parent[ulp_u] = ulp_v;
        }
        else if (rank[ulp_v] < rank[ulp_u]) {
            parent[ulp_v] = ulp_u;
        }
        else {
            parent[ulp_v] = ulp_u;
            rank[ulp_u]++;
        }
    }

    void unionBySize(int u, int v) {
        int ulp_u = findUPar(u);
        int ulp_v = findUPar(v);
        if (ulp_u == ulp_v) return;
        if (size[ulp_u] < size[ulp_v]) {
            parent[ulp_u] = ulp_v;
            size[ulp_v] += size[ulp_u];
        }
        else {
            parent[ulp_v] = ulp_u;
            size[ulp_u] += size[ulp_v];
        }
    }
};
```
Kruskal’s Algorithm
```
int spanningTree(int V, vector<vector<int>> adj[]) {
    vector<pair<int, pair<int, int>>> edges;
    for (int i = 0; i < V; i++) {
        for (auto it : adj[i]) {
            int adjNode = it[0];
            int wt = it[1];
            int node = i;
            edges.push_back({wt, {node, adjNode}});
        }
    }
    DisjointSet ds(V);
    sort(edges.begin(), edges.end());
    int mstWt = 0;
    for (auto it : edges) {
        int wt = it.first;
        int u = it.second.first;
        int v = it.second.second;
        if (ds.findUPar(u) != ds.findUPar(v)) {
            mstWt += wt;
            ds.unionBySize(u, v);
        }
    }
    return mstWt;
}
```
Number of Operations to Make Network Connected
```
void f(int node,vector<vector<int>>& g,vector<bool> &vis){
    vis[node]=true;
    for(auto it:g[node]){
        if(!vis[it]) f(it,g,vis);
    }
}

int makeConnected(int n, vector<vector<int>>& c) {
    if(c.size()<n-1) return -1;
    vector<vector<int>> g(n);
    for(auto it:c) g[it[0]].push_back(it[1]),g[it[1]].push_back(it[0]);
    vector<bool> vis(n);
    int a=0;
    for(int i=0;i<n;i++){
        if(!vis[i]) f(i,g,vis),a++;
    }
    return a-1;
}
```
Most Stones Removed with Same Row or Column
```
int par[20001];
int sz[20001];

int parent(int n){
    if(par[n]==n) return n;
    return par[n]=parent(par[n]);
}

void add(int u,int v){
    int u_par=parent(u);
    int v_par=parent(v);
    if(u_par==v_par) return;
    if(sz[u_par]>sz[v_par]){
        par[v_par]=u_par;
        sz[u_par]+=sz[v_par];
    }
    else{
        par[u_par]=v_par;
        sz[v_par]+=sz[u_par];
    }
}

int removeStones(vector<vector<int>>& a) {
    int c=0;
    for(int i=0;i<20001;i++){
        par[i]=i;
        sz[i]=0;
    }
    int row=INT_MIN;
    for(auto it:a) row=max(row,it[0]);
    unordered_set<int> s;
    for(auto it:a){
        add(it[0],it[1]+row+1);
        s.insert(it[0]);
        s.insert(it[1]+row+1);
    }
    for(auto it:s) if(parent(it)==it) c++;
    return a.size()-c;
}
```
Accounts Merge
```
int p[1001];
int sz[1001];

int par(int n){
    if(p[n]==n) return n;
    return p[n]=par(p[n]);
}

void add(int u,int v){
    int pu=par(u);
    int pv=par(v);
    if(pu==pv) return;
    if(sz[pu]>sz[pv]){
        p[pv]=pu;
        sz[pu]+=sz[pv];
    }
    else{
        p[pu]=pv;
        sz[pv]+=sz[pu];
    }
}

vector<vector<string>> accountsMerge(vector<vector<string>>& a) {
    for(int i=0;i<1001;i++){
        p[i]=i;
        sz[i]=0;
    }
    unordered_map<string,int> mp;
    for(int i=0;i<a.size();i++){
        for(int j=1;j<a[i].size();j++){
            if(mp.find(a[i][j])==mp.end()) mp[a[i][j]]=i;
            else add(i,mp[a[i][j]]);
        }
    }
    unordered_map<int,set<string>> acc;
    for(auto it:mp){
        acc[par(it.second)].insert(it.first);
    }
    vector<vector<string>> ans;
    vector<string> usr;
    for(auto it:acc){
        cout<<a[it.first][0]<<" ";
        for(auto j:it.second) cout<<j<<" ";
        cout<<"\n";
        int pa=par(it.first);
        if(it.first==pa) usr.push_back(a[it.first][0]);          
        for(auto j:it.second) usr.push_back(j);
        ans.push_back(usr);
        usr.clear();
    }
    return ans;
}
```
Number of island II
```
```
Making A Large Island
```
int p[250001];
int sz[250001];

int par(int n){
    if(p[n]==n) return n;
    return p[n]=par(p[n]);
}

void add(int u,int v){
    int pu=par(u);
    int pv=par(v);
    if(pu==pv) return;
    if(sz[pu]>sz[pv]){
        p[pv]=pu;
        sz[pu]+=sz[pv];
    }
    else{
        p[pu]=pv;
        sz[pv]+=sz[pu];
    }
}

int largestIsland(vector<vector<int>>& g) {
    for(int i=0;i<250001;i++){
        p[i]=i;
        sz[i]=1;
    }
    int r=g.size(),c=g[0].size(),xa,ya,pa,sum,ans=0;
    set<int> s;
    int x_arr[]={0,0,1,-1},y_arr[]={1,-1,0,0};
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            if(g[i][j]){
                for(int k=0;k<4;k++){
                    xa=i+x_arr[k];
                    ya=j+y_arr[k];
                    if(xa<0 || xa>=r || ya<0 || ya>=c || !g[xa][ya]) continue;
                    add(i*c+j,xa*c+ya);
                }
            }
        }
    }

    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            if(!g[i][j]){
                sum=0;
                s.clear();
                for(int k=0;k<4;k++){
                    xa=i+x_arr[k];
                    ya=j+y_arr[k];
                    if(xa<0 || xa>=r || ya<0 || ya>=c || !g[xa][ya]) continue;
                    pa=par(xa*c+ya);
                    if(s.find(pa)==s.end()) sum+=sz[pa];
                    s.insert(pa);
                }
                ans=max(ans,sum+1);
            }
        }
    }
    if(!ans) return r*c;
    return ans;
}
```
Swim in rising water
```
```
Bridges in Graph
```
int timer=1;

void f(vector<int> g[],vector<bool> &vis,vector<int> &tin,vector<int> &low,vector<vector<int>> &b,int node,int p){
    vis[node]=true;
    tin[node]=low[node]=timer;
    timer++;
    for(auto it:g[node]){
        if(it==p) continue;
        if(!vis[it]){
            f(g,vis,tin,low,b,it,node);
            low[node]=min(low[node],low[it]);
            if(tin[node]<low[it]) b.push_back({node,it});
        }
        else{
            low[node]=min(low[node],low[it]);
        }
    }
}

vector<vector<int>> criticalConnections(int n, vector<vector<int>>& c) {
    vector<vector<int>> b;
    vector<int> g[n];
    for(auto it:c){
        g[it[0]].push_back(it[1]);
        g[it[1]].push_back(it[0]);
    }
    vector<bool> vis(n);
    vector<int> tin(n);
    vector<int> low(n);
    f(g,vis,tin,low,b,0,-1);
    return b;
}
```
Articulation Point
```
```
Kosaraju's Algorithm
```
void dfs(int node, vector<int> &vis, vector<int> adj[], stack<int> &st) {
    vis[node] = 1;
    for (auto it : adj[node]) {
        if (!vis[it]) {
            dfs(it, vis, adj, st);
        }
    }
    st.push(node);
}

void dfs3(int node, vector<int> &vis, vector<int> adjT[]) {
    vis[node] = 1;
    for (auto it : adjT[node]) {
        if (!vis[it]) {
            dfs3(it, vis, adjT);
        }
    }
}

int kosaraju(int V, vector<int> adj[])
{
    vector<int> vis(V, 0);
    stack<int> st;
    for (int i = 0; i < V; i++) {
        if (!vis[i]) {
            dfs(i, vis, adj, st);
        }
    }
    vector<int> adjT[V];
    for (int i = 0; i < V; i++) {
        vis[i] = 0;
        for (auto it : adj[i]) {
            adjT[it].push_back(i);
        }
    }
    int scc = 0;
    while (!st.empty()) {
        int node = st.top();
        st.pop();
        if (!vis[node]) {
            scc++;
            dfs3(node, vis, adjT);
        }
    }
    return scc;
}
```

# Dynamic Programming

Climbing Stars
```
int f(int n,vector<int> &dp){
    if(n==0) return 1;
    if(n<0) return 0;
    if(dp[n]!=-1) return dp[n];
    return dp[n]=f(n-1,dp)+f(n-2,dp);
}

int climbStairs(int n) {
    vector<int> dp(n+1,-1);
    return f(n,dp);
}
```
Frog Jump
```
int f(int i,vector<int> &h,vector<int> &dp){
    if(i==0) return dp[i]=0;
    if(dp[i]!=-1) return dp[i];
    int one=abs(h[i]-h[i-1])+f(i-1,h,dp);
    int two=INT_MAX;
    if(i>1) two=abs(h[i]-h[i-2])+f(i-2,h,dp);
    return dp[i]=min(one,two);
}

int frogJump(int n, vector<int> &heights){
    vector<int> dp(n,-1);
    return f(n-1,heights,dp);
}
```
Frog Jump with k distances
```
int f(int i,vector<int> &h,vector<int> &dp,int k){
    if(i==0) return dp[i]=0;
    if(dp[i]!=-1) return dp[i];
    int mi=INT_MAX;
    for(int j=1;j<=k;j++){
        if(i-j>=0) mi=min(mi,abs(h[i]-h[i-j])+f(i-j,h,dp));
    }
    return dp[i]=mi;
}

int frogJump(int n, vector<int> &heights,int k){
    vector<int> dp(n,-1);
    return f(n-1,heights,dp,k);
}
```
Max sum of non-adjacent elements
```
int f(int ind,vector<int>& nums,vector<int> &dp){  
    if(ind<0) return 0;
    if(ind==0) return dp[ind]=nums[ind];
    if(dp[ind]!=-1) return dp[ind];
    int pick=nums[ind]+f(ind-2,nums,dp);
    int notPick=f(ind-1,nums,dp);
    return dp[ind]=max(pick,notPick);
}

int rob(vector<int>& nums) {
    vector<int> dp(nums.size(),-1);
    return f(nums.size()-1,nums,dp);
}
```
Max sum of non-adjacent circular elements
```
int f(int ind,vector<int>& nums,vector<int> &dp){    
    if(ind<0) return 0;
    if(ind==0) return dp[ind]=nums[ind];
    if(dp[ind]!=-1) return dp[ind];
    int pick=nums[ind]+f(ind-2,nums,dp);
    int notPick=f(ind-1,nums,dp);
    return dp[ind]=max(pick,notPick);
}

int rob(vector<int>& nums) {
    if(nums.size()==1) return nums[0];
    vector<int> n1,n2;
    for(int i=0;i<nums.size();i++){
        if(i!=0) n1.push_back(nums[i]);
        if(i!=nums.size()-1) n2.push_back(nums[i]);
    }
    vector<int> dp1(n1.size(),-1);
    vector<int> dp2(n2.size(),-1);
    return max(f(n1.size()-1,n1,dp1),f(n2.size()-1,n2,dp2));
}
```
Ninja's Training
```
int f(int day, int last, vector<vector<int>> &points, vector<vector<int>> &dp) {
  if (dp[day][last] != -1) return dp[day][last];
  if (day == 0) {
    int maxi = 0;
    for (int i = 0; i <= 2; i++) {
      if (i != last)
        maxi = max(maxi, points[0][i]);
    }
    return dp[day][last] = maxi;
  }

  int maxi = 0;
  for (int i = 0; i <= 2; i++) {
    if (i != last) {
      int activity = points[day][i] + f(day - 1, i, points, dp);
      maxi = max(maxi, activity);
    }
  }
  return dp[day][last] = maxi;
}
```
Grid Unique Paths
```
int f(int i,int j,vector<vector<int>> &dp){
    if(i<0 || j<0) return 0;  
    if(dp[i][j]!=-1) return dp[i][j];
    if(i==0 && j==0) return 1;
    return dp[i][j]=f(i-1,j,dp)+f(i,j-1,dp);
}

int uniquePaths(int m, int n) {
    vector<vector<int>> dp(m,vector<int>(n,-1));
    return f(m-1,n-1,dp);
}
```
Grid Unique Paths with obstacles
```
int solve(int i,int j,vector<vector<int>>& m,vector<vector<int>> &dp){
    if(i<0 || j<0) return 0;
    if(m[i][j]==1) return 0;
    if(i==0 && j==0) return 1;
    if(dp[i][j]!=-1) return dp[i][j];
    return dp[i][j]=solve(i-1,j,m,dp)+solve(i,j-1,m,dp);
}

int uniquePathsWithObstacles(vector<vector<int>>& m) {
    vector<vector<int>> dp(m.size(),vector<int>(m[0].size(),-1));
    return solve(m.size()-1,m[0].size()-1,m,dp);
}
```
Minimum path sum in Grid
```
int f(vector<vector<int>>& g,int i,int j,vector<vector<int>>& dp){
    if(i==0 && j==0) return g[i][j];
    if(i<0 || j<0) return 1e9;
    if(dp[i][j]!=-1) return dp[i][j];
    return dp[i][j]=g[i][j]+min(f(g,i-1,j,dp),f(g,i,j-1,dp));
}
int minPathSum(vector<vector<int>>& g) {
    vector<vector<int>> dp(g.size(),vector<int>(g[0].size(),-1));
    return f(g,g.size()-1,g[0].size()-1,dp);
}
```
Ninja and his friends
```
int maxChocoUtil(int i, int j1, int j2, int n, int m, vector<vector<int>> &grid, vector<vector<vector<int>>> &dp) {
    if (j1 < 0 || j1 >= m || j2 < 0 || j2 >= m) return -1e9;
    if (i == n - 1) {
        if (j1 == j2) return grid[i][j1];
        return grid[i][j1] + grid[i][j2];
    }

    if (dp[i][j1][j2] != -1) return dp[i][j1][j2];

    int maxi = INT_MIN;
    for (int di = -1; di <= 1; di++) {
        for (int dj = -1; dj <= 1; dj++) {
            int ans = grid[i][j1] + maxChocoUtil(i + 1, j1 + di, j2 + dj, n, m, grid, dp);
            if (j1 != j2)  ans += grid[i][j2]
            maxi = max(maxi, ans);
        }
    }
    return dp[i][j1][j2] = maxi;
}
```
Subset sum equal to target	
```
bool subsetSumUtil(int ind, int target, vector<int>& arr, vector<vector<int>>& dp) {
    if (target == 0) return true;
    if (ind == 0) return arr[0] == target;
    if (dp[ind][target] != -1) return dp[ind][target];
    bool notTaken = subsetSumUtil(ind - 1, target, arr, dp);
    bool taken = false;
    if (arr[ind] <= target) taken = subsetSumUtil(ind - 1, target - arr[ind], arr, dp);
    return dp[ind][target] = notTaken || taken;
}

bool subsetSumToK(int n, int k, vector<int>& arr) {
    vector<vector<int>> dp(n, vector<int>(k + 1, -1));
    return subsetSumUtil(n - 1, k, arr, dp);
}
```	

Partition Equal Subset Sum 	
```
bool subsetSumUtil(int ind, int target, vector<int>& arr, vector<vector<int>>& dp) {
    if (target == 0) return true;
    if (ind == 0) return arr[0] == target;
    if (dp[ind][target] != -1) return dp[ind][target];
    bool notTaken = subsetSumUtil(ind - 1, target, arr, dp);
    bool taken = false;
    if (arr[ind] <= target) taken = subsetSumUtil(ind - 1, target - arr[ind], arr, dp);
    return dp[ind][target] = notTaken || taken;
}

bool canPartition(int n, vector<int>& arr) {
    int totSum = 0;
    for (int i = 0; i < n; i++) totSum += arr[i];
    if (totSum % 2 == 1) return false;
    else {
        int k = totSum / 2;
        vector<vector<int>> dp(n, vector<int>(k + 1, -1));
        return subsetSumUtil(n - 1, k, arr, dp);
    }
}
```	
	
Partition Set Into 2 Subsets With Min Absolute Sum Diff
```
bool subsetSumUtil(int ind, int target, vector<int>& arr, vector<vector<int>>& dp) {
    if (target == 0) return dp[ind][target] = true;
    if (ind == 0) return dp[ind][target] = (arr[0] == target);
    if (dp[ind][target] != -1) return dp[ind][target];
    bool notTaken = subsetSumUtil(ind - 1, target, arr, dp);
    bool taken = false;
    if (arr[ind] <= target) taken = subsetSumUtil(ind - 1, target - arr[ind], arr, dp);
    return dp[ind][target] = notTaken || taken;
}

int minSubsetSumDifference(vector<int>& arr, int n) {
    int totSum = 0;
    for (int i = 0; i < n; i++) totSum += arr[i];
    vector<vector<int>> dp(n, vector<int>(totSum + 1, -1));
    for (int i = 0; i <= totSum; i++) bool dummy = subsetSumUtil(n - 1, i, arr, dp);
    int mini = 1e9;
    for (int i = 0; i <= totSum; i++) {
        if (dp[n - 1][i] == true) {
            int diff = abs(i - (totSum - i));
            mini = min(mini, diff);
        }
    }
    return mini;
}
```
	
Count Subsets with Sum K
```
int findWaysUtil(int ind, int target, vector<int>& arr, vector<vector<int>>& dp) {
    if (target == 0) return 1;
    if (ind == 0) return (arr[0] == target) ? 1 : 0;
    if (dp[ind][target] != -1) return dp[ind][target];
    int notTaken = findWaysUtil(ind - 1, target, arr, dp);
    int taken = 0;
    if (arr[ind] <= target) taken = findWaysUtil(ind - 1, target - arr[ind], arr, dp);
    return dp[ind][target] = notTaken + taken;
}

int findWays(vector<int>& num, int k) {
    int n = num.size();
    vector<vector<int>> dp(n, vector<int>(k + 1, -1));
    return findWaysUtil(n - 1, k, num, dp);
}
```	

Count Partitions with Given Difference
```
int findWaysUtil(int ind, int target, vector<int>& arr, vector<vector<int>> &dp){
    if(ind == 0){
            if(target==0 && arr[0]==0) return 2;
            if(target==0 || target == arr[0]) return 1;
            return 0;
    }
    if(dp[ind][target]!=-1) return dp[ind][target];
    int notTaken = findWaysUtil(ind-1,target,arr,dp);
    int taken = 0;
    if(arr[ind]<=target) taken = findWaysUtil(ind-1,target-arr[ind],arr,dp);
    return dp[ind][target]= notTaken + taken;
}

int findWays(vector<int> &num, int k){
    int n = num.size();
    vector<vector<int>> dp(n,vector<int>(k+1,-1));
    return findWaysUtil(n-1,k,num,dp);
}
```	

0/1 Knapsack		
```
int knapsackUtil(vector<int>& wt, vector<int>& val, int ind, int W, vector<vector<int>>& dp) {
    if (ind == 0 || W == 0) return 0;
    if (dp[ind][W] != -1) return dp[ind][W];
    int notTaken = knapsackUtil(wt, val, ind - 1, W, dp);
    int taken = 0;
    if (wt[ind] <= W) taken = val[ind] + knapsackUtil(wt, val, ind - 1, W - wt[ind], dp);
    return dp[ind][W] = max(notTaken, taken);
}

int knapsack(vector<int>& wt, vector<int>& val, int n, int W) {
    vector<vector<int>> dp(n, vector<int>(W + 1, -1));
    return knapsackUtil(wt, val, n - 1, W, dp);
}
```

Minimum Coins
```
int minimumElementsUtil(vector<int>& arr, int ind, int T, vector<vector<int>>& dp){
    if(ind == 0){
        if(T % arr[0] == 0) return T / arr[0];
        else return 1e9;
    }
    if(dp[ind][T] != -1) return dp[ind][T];
    int notTaken = 0 + minimumElementsUtil(arr, ind - 1, T, dp);
    int taken = 1e9;
    if(arr[ind] <= T) taken = 1 + minimumElementsUtil(arr, ind, T - arr[ind], dp);
    return dp[ind][T] = min(notTaken, taken);
}

int minimumElements(vector<int>& arr, int T){
    int n = arr.size();
    vector<vector<int>> dp(n, vector<int>(T + 1, -1));
    int ans =  minimumElementsUtil(arr, n - 1, T, dp);
    if(ans >= 1e9) return -1;
    return ans;
}
```	
	
Target Sum
```
int countPartitionsUtil(int ind, int target, vector<int>& arr, vector<vector<int>>& dp) {
    if (ind == 0) {
        if (target == 0 && arr[0] == 0) return 2;
        if (target == 0 || target == arr[0]) return 1;
        return 0;
    }
    if (dp[ind][target] != -1) return dp[ind][target];
    int notTaken = countPartitionsUtil(ind - 1, target, arr, dp);
    int taken = 0;
    if (arr[ind] <= target) taken = countPartitionsUtil(ind - 1, target - arr[ind], arr, dp);
    return dp[ind][target] = (notTaken + taken);
}

int targetSum(int n, int target, vector<int>& arr) {
    int totSum = 0;
    for (int i = 0; i < arr.size(); i++) totSum += arr[i];
    if (totSum - target < 0) return 0;
    if ((totSum - target) % 2 == 1) return 0;
    int s2 = (totSum - target) / 2;
    vector<vector<int>> dp(n, vector<int>(s2 + 1, -1));
    return countPartitionsUtil(n - 1, s2, arr, dp);
}
```

Min Coin Change Count Ways
```
long countWaysToMakeChangeUtil(vector<int>& arr, int ind, int T, vector<vector<long>>& dp) {
    if (ind == 0) return (T % arr[0] == 0);
    if (dp[ind][T] != -1) return dp[ind][T];
    long notTaken = countWaysToMakeChangeUtil(arr, ind - 1, T, dp);
    long taken = 0;
    if (arr[ind] <= T) taken = countWaysToMakeChangeUtil(arr, ind, T - arr[ind], dp);
    return dp[ind][T] = notTaken + taken;
}

long countWaysToMakeChange(vector<int>& arr, int n, int T) {
    vector<vector<long>> dp(n, vector<long>(T + 1, -1));
    return countWaysToMakeChangeUtil(arr, n - 1, T, dp);
}
```		
	
Unbounded Knapsack
```
int knapsackUtil(vector<int>& wt, vector<int>& val, int ind, int W, vector<vector<int>>& dp) {
    if (ind == 0) return (W / wt[0]) * val[0];
    if (dp[ind][W] != -1) return dp[ind][W];
    int notTaken = 0 + knapsackUtil(wt, val, ind - 1, W, dp);
    int taken = INT_MIN;
    if (wt[ind] <= W) taken = val[ind] + knapsackUtil(wt, val, ind, W - wt[ind], dp);
    return dp[ind][W] = max(notTaken, taken);
}

int unboundedKnapsack(int n, int W, vector<int>& val, vector<int>& wt) {
    vector<vector<int>> dp(n, vector<int>(W + 1, -1));
    return knapsackUtil(wt, val, n - 1, W, dp);
}
```

Rod Cutting Problem
```
```

Longest Common Subsequence	
```
int lcsUtil(string& s1, string& s2, int ind1, int ind2, vector<vector<int>>& dp) {
    if (ind1 < 0 || ind2 < 0) return 0;
    if (dp[ind1][ind2] != -1) return dp[ind1][ind2];
    if (s1[ind1] == s2[ind2]) return dp[ind1][ind2] = 1 + lcsUtil(s1, s2, ind1 - 1, ind2 - 1, dp);
    else return dp[ind1][ind2] = max(lcsUtil(s1, s2, ind1, ind2 - 1, dp), lcsUtil(s1, s2, ind1 - 1, ind2, dp));
}

int lcs(string s1, string s2) {
    int n = s1.size();
    int m = s2.size();
    vector<vector<int>> dp(n, vector<int>(m, -1));
    return lcsUtil(s1, s2, n - 1, m - 1, dp);
}
```

Print Longest Common Subsequence	
```
void lcs(string s1, string s2) {
    int n = s1.size();
    int m = s2.size();
    vector < vector < int >> dp(n + 1, vector < int > (m + 1, 0));
    for (int i = 0; i <= n; i++) dp[i][0] = 0;
    for (int i = 0; i <= m; i++) dp[0][i] = 0;
    for (int ind1 = 1; ind1 <= n; ind1++) {
        for (int ind2 = 1; ind2 <= m; ind2++) {
            if (s1[ind1 - 1] == s2[ind2 - 1]) dp[ind1][ind2] = 1 + dp[ind1 - 1][ind2 - 1];
            else dp[ind1][ind2] = 0 + max(dp[ind1 - 1][ind2], dp[ind1][ind2 - 1]);
        }
    }
    int len = dp[n][m];
    int i = n;
    int j = m;
    int index = len - 1;
    string str = "";
    for (int k = 1; k <= len; k++) str += "$";
    while (i > 0 && j > 0) {
        if (s1[i - 1] == s2[j - 1]) {
            str[index] = s1[i - 1];
            index--;
            i--;
            j--;
        } 
        else if (s1[i - 1] > s2[j - 1]) i--;
        else j--;
    }
    cout << str;
}

```

Longest Common Substring 	
```
int lcs(string &s1, string &s2){
    int n = s1.size();
    int m = s2.size();
    vector> dp(n+1, vector(m+1, 0));
    int ans = 0;
    for(int i = 1; i <= n; i++){
        for(int j = 1; j <= m; j++){
            if(s1[i-1] == s2[j-1]){
                int val = 1 + dp[i-1][j-1];
                dp[i][j] = val;
                ans = max(ans, val);
            }
            else dp[i][j] = 0;
        }
    }
    return ans;
}
```

Longest Palindromic Subsequence	
```
int longestPalindromeSubsequence(string s) {
    string t = s;
    reverse(s.begin(), s.end());
    return lcs(s, t);
}
```

Minimum insertions to make string palindrome
```
int minInsertion(string s) {
    int n = s.size();
    int k = longestPalindromeSubsequence(s);
    return n - k;
}
```

Minimum Insertions/Deletions to Convert String	
```
int canYouMake(string str1, string str2) {
    int n = str1.size();
    int m = str2.size();
    int k = lcs(str1, str2);
    return (n - k) + (m - k);
}
```

Shortest Common Supersequence	
```
```

Distinct Subsequences	
```
int countUtil(string s1, string s2, int ind1, int ind2, vector<vector<int>>& dp) {
    if (ind2 < 0) return 1;
    if (ind1 < 0) return 0;
    if (dp[ind1][ind2] != -1) return dp[ind1][ind2];
    int result = 0;
    if (s1[ind1] == s2[ind2]) {
        int leaveOne = countUtil(s1, s2, ind1 - 1, ind2 - 1, dp);
        int stay = countUtil(s1, s2, ind1 - 1, ind2, dp);
        result = (leaveOne + stay) % prime;
    } 
    else {
        result = countUtil(s1, s2, ind1 - 1, ind2, dp);
    }
    dp[ind1][ind2] = result;
    return result;
}

int subsequenceCounting(string &s1, string &s2, int lt, int ls) {
    vector<vector<int>> dp(lt, vector<int>(ls, -1));
    return countUtil(s1, s2, lt - 1, ls - 1, dp);
}
```

Edit Distance	
```
int editDistanceUtil(string& S1, string& S2, int i, int j, vector<vector<int>>& dp) {
    if (i < 0) return j + 1;
    if (j < 0) return i + 1;
    if (dp[i][j] != -1) return dp[i][j];
    if (S1[i] == S2[j]) return dp[i][j] = 0 + editDistanceUtil(S1, S2, i - 1, j - 1, dp);
    else return dp[i][j] = 1 + min({
                               editDistanceUtil(S1, S2, i - 1, j - 1, dp),
                               editDistanceUtil(S1, S2, i - 1, j, dp),
                               editDistanceUtil(S1, S2, i, j - 1, dp)
                               });
}

int editDistance(string& S1, string& S2) {
    int n = S1.size();
    int m = S2.size();
    vector<vector<int>> dp(n, vector<int>(m, -1));
    return editDistanceUtil(S1, S2, n - 1, m - 1, dp);
}
```

Wildcard Matching
```
bool isAllStars(string &S1, int i) {
    for (int j = 0; j <= i; j++) {
        if (S1[j] != '*') return false;
    }
    return true;
}

bool wildcardMatchingUtil(string &S1, string &S2, int i, int j, vector<vector<bool>> &dp) {
    if (i < 0 && j < 0) return true;
    if (i < 0 && j >= 0) return false;
    if (j < 0 && i >= 0) return isAllStars(S1, i);
    if (dp[i][j] != -1) return dp[i][j];
    if (S1[i] == S2[j] || S1[i] == '?') return dp[i][j] = wildcardMatchingUtil(S1, S2, i - 1, j - 1, dp);
    else {
        if (S1[i] == '*') return dp[i][j] = wildcardMatchingUtil(S1, S2, i - 1, j, dp) || wildcardMatchingUtil(S1, S2, i, j - 1, dp);
        else return false;
    }
}

bool wildcardMatching(string &S1, string &S2) {
    int n = S1.size();
    int m = S2.size();
    vector<vector<bool>> dp(n, vector<bool>(m, -1));
    return wildcardMatchingUtil(S1, S2, n - 1, m - 1, dp);
}
```

Best Time to Buy and Sell Stock		
```
int maximumProfit(vector<int> &Arr){
	int maxProfit = 0;
	int mini = Arr[0];
	for(int i=1;i<Arr.size();i++){
        int curProfit = Arr[i] - mini;
        maxProfit = max(maxProfit,curProfit);
        mini = min(mini,Arr[i]);
        }
	return maxProfit;
}
```

Buy and Sell Stock any number of times	
```
long getAns(long *Arr, int ind, int buy, int n, vector<vector<long>> &dp) {
    if (ind == n) return 0;
    if (dp[ind][buy] != -1) return dp[ind][buy];
    long profit = 0;
    if (buy == 0) profit = max(0 + getAns(Arr, ind + 1, 0, n, dp), -Arr[ind] + getAns(Arr, ind + 1, 1, n, dp));
    if (buy == 1) profit = max(0 + getAns(Arr, ind + 1, 1, n, dp), Arr[ind] + getAns(Arr, ind + 1, 0, n, dp));
    return dp[ind][buy] = profit;
}

long getMaximumProfit(long *Arr, int n) {
    vector<vector<long>> dp(n, vector<long>(2, -1));
    if (n == 0) return 0;
    long ans = getAns(Arr, 0, 0, n, dp);
    return ans;
}
```

Buy and Sell Stocks 2 transactions	
```
int getAns(vector<int>& Arr, int n, int ind, int buy, int cap, vector<vector<vector<int>>>& dp) {
    if (ind == n || cap == 0) return 0;
    if (dp[ind][buy][cap] != -1) return dp[ind][buy][cap];
    int profit;
    if (buy == 0) profit = max(0 + getAns(Arr, n, ind + 1, 0, cap, dp),-Arr[ind] + getAns(Arr, n, ind + 1, 1, cap, dp));
    if (buy == 1) profit = max(0 + getAns(Arr, n, ind + 1, 1, cap, dp),Arr[ind] + getAns(Arr, n, ind + 1, 0, cap - 1, dp));
    return dp[ind][buy][cap] = profit;
}

int maxProfit(vector<int>& prices, int n) {
    vector<vector<vector<int>>> dp(n, vector<vector<int>>(2, vector<int>(3, -1)));
    return getAns(prices, n, 0, 0, 2, dp);
}
```
	
Buy and Stock Sell K transactions	
```
int getAns(vector<int>& Arr, int n, int ind, int buy, int cap, vector<vector<vector<int>>>& dp) {
    if (ind == n || cap == 0) return 0;
    if (dp[ind][buy][cap] != -1) return dp[ind][buy][cap];
    int profit;
    if (buy == 0) profit = max(0 + getAns(Arr, n, ind + 1, 0, cap, dp),-Arr[ind] + getAns(Arr, n, ind + 1, 1, cap, dp));
    if (buy == 1) profit = max(0 + getAns(Arr, n, ind + 1, 1, cap, dp),Arr[ind] + getAns(Arr, n, ind + 1, 0, cap - 1, dp));
    return dp[ind][buy][cap] = profit;
}

int maximumProfit(vector<int>& prices, int n, int k) {
    vector<vector<vector<int>>> dp(n,vector<vector<int>>(2, vector<int>(k + 1, -1)));
    return getAns(prices, n, 0, 0, k, dp);
}
```
	
Buy and Sell Stocks With Cooldown	
```
int getAns(vector<int> Arr, int ind, int buy, int n, vector<vector<int>> &dp) {
    if (ind >= n) return 0;
    if (dp[ind][buy] != -1) return dp[ind][buy];
    int profit;
    if (buy == 0) profit = max(0 + getAns(Arr, ind + 1, 0, n, dp), -Arr[ind] + getAns(Arr, ind + 1, 1, n, dp));
    if (buy == 1) profit = max(0 + getAns(Arr, ind + 1, 1, n, dp), Arr[ind] + getAns(Arr, ind + 2, 0, n, dp));
    return dp[ind][buy] = profit;
}

int stockProfit(vector<int> &Arr) {
    int n = Arr.size();
    vector<vector<int>> dp(n, vector<int>(2, -1));
    int ans = getAns(Arr, 0, 0, n, dp);
    return ans;
}
```
	
Buy and Sell Stocks With Transaction Fee
```
int getAns(vector<int> &Arr, int ind, int buy, int n, int fee, vector<vector<int>> &dp) {
    if (ind == n) return 0;
    if (dp[ind][buy] != -1) return dp[ind][buy];
    int profit;
    if (buy == 0) profit = max(0 + getAns(Arr, ind + 1, 0, n, fee, dp), -Arr[ind] + getAns(Arr, ind + 1, 1, n, fee, dp));
    if (buy == 1) profit = max(0 + getAns(Arr, ind + 1, 1, n, fee, dp), Arr[ind] - fee + getAns(Arr, ind + 1, 0, n, fee, dp));
    return dp[ind][buy] = profit;
}

int maximumProfit(int n, int fee, vector<int> &Arr) {
    vector<vector<int>> dp(n, vector<int>(2, -1));
    if (n == 0) return 0;
    int ans = getAns(Arr, 0, 0, n, fee, dp);
    return ans;
}
```

Longest Increasing Subsequence		
```
int getAns(int arr[], int n, int ind, int prev_index, vector<vector<int>>& dp) {
    if (ind == n) return 0;
    if (dp[ind][prev_index + 1] != -1) return dp[ind][prev_index + 1];
    int notTake = 0 + getAns(arr, n, ind + 1, prev_index, dp);
    int take = 0;
    if (prev_index == -1 || arr[ind] > arr[prev_index]) take = 1 + getAns(arr, n, ind + 1, ind, dp);
    return dp[ind][prev_index + 1] = max(notTake, take);
}

int longestIncreasingSubsequence(int arr[], int n) {
    vector<vector<int>> dp(n, vector<int>(n + 1, -1));
    return getAns(arr, n, 0, -1, dp);
}
```

Printing Longest Increasing Subsequence	
```
int longestIncreasingSubsequence(int arr[], int n){
    vector<int> dp(n,1);
    vector<int> hash(n,1);
    for(int i=0; i<=n-1; i++){
        hash[i] = i;
        for(int prev_index = 0; prev_index <=i-1; prev_index ++){
            if(arr[prev_index]<arr[i] && 1 + dp[prev_index] > dp[i]){
                dp[i] = 1 + dp[prev_index];
                hash[i] = prev_index;
            }
        }
    }
    int ans = -1;
    int lastIndex =-1;
    for(int i=0; i<=n-1; i++){
        if(dp[i]> ans){
            ans = dp[i];
            lastIndex = i;
        }
    }
    vector<int> temp;
    temp.push_back(arr[lastIndex]);
    while(hash[lastIndex] != lastIndex){
        lastIndex = hash[lastIndex];
        temp.push_back(arr[lastIndex]);    
    }
    reverse(temp.begin(),temp.end());
    for(int i=0; i<temp.size(); i++) cout<<temp[i]<<" ";
    return ans;
}
```

Longest Increasing Subsequence Binary Search
```
int longestIncreasingSubsequence(int arr[], int n) {
    vector<int> temp;
    temp.push_back(arr[0]);
    int len = 1;
    for (int i = 1; i < n; i++) {
        if (arr[i] > temp.back()) {
            temp.push_back(arr[i]);
            len++;
        } 
        else {
            int ind = lower_bound(temp.begin(), temp.end(), arr[i]) - temp.begin();
            temp[ind] = arr[i];
        }
    }
    return len;
}
```

Largest Divisible Subset		
```
vector<int> divisibleSet(vector<int>& arr) {
    int n = arr.size();
    sort(arr.begin(), arr.end());
    vector<int> dp(n, 1);   
    vector<int> hash(n, i); 
    for (int i = 0; i < n; i++) {
        hash[i] = i; // Initialize with the current index
        for (int prev_index = 0; prev_index < i; prev_index++) {
            if (arr[i] % arr[prev_index] == 0 && 1 + dp[prev_index] > dp[i]) {
                dp[i] = 1 + dp[prev_index];
                hash[i] = prev_index;
            }
        }
    }
    int ans = -1;
    int lastIndex = -1;
    for (int i = 0; i < n; i++) {
        if (dp[i] > ans) {
            ans = dp[i];
            lastIndex = i;
        }
    }
    vector<int> temp;
    temp.push_back(arr[lastIndex]);
    while (hash[lastIndex] != lastIndex) {
        lastIndex = hash[lastIndex];
        temp.push_back(arr[lastIndex]);
    }
    reverse(temp.begin(), temp.end());
    return temp;
}
```

Longest String Chain	
```
bool compare(string& s1, string& s2){
    if(s1.size() != s2.size() + 1) return false;
    int first = 0;
    int second = 0;
    while(first < s1.size()){
        if(second < s2.size() && s1[first] == s2[second]){
            first ++;
            second ++;
        }
        else first ++;
    }
    if(first == s1.size() && second == s2.size()) return true;
    else return false; 
}

bool comp(string& s1, string& s2){
    return s1.size() < s2.size();
}

int longestStrChain(vector<string>& arr){
    int n = arr.size();
    sort(arr.begin(), arr.end(),comp);
    vector<int> dp(n,1);
    int maxi = 1;
    for(int i=0; i<=n-1; i++){
        for(int prev_index = 0; prev_index <=i-1; prev_index ++){
            if( compare(arr[i], arr[prev_index]) && 1 + dp[prev_index] > dp[i]){
                dp[i] = 1 + dp[prev_index];
            }
        }
        if(dp[i] > maxi) maxi = dp[i];
    }
    return maxi;
}
```

Longest Bitonic Subsequence	
```
int longestBitonicSequence(vector<int>& arr, int n) {
    vector<int> dp1(n, 1); 
    vector<int> dp2(n, 1); 
    for (int i = 0; i < n; i++) {
        for (int prev_index = 0; prev_index < i; prev_index++) {
            if (arr[prev_index] < arr[i]) {
                dp1[i] = max(dp1[i], 1 + dp1[prev_index]);
            }
        }
    }
    for (int i = n - 1; i >= 0; i--) {
        for (int prev_index = n - 1; prev_index > i; prev_index--) {
            if (arr[prev_index] < arr[i]) {
                dp2[i] = max(dp2[i], 1 + dp2[prev_index]);
            }
        }
    }
    int maxi = -1;
    for (int i = 0; i < n; i++) maxi = max(maxi, dp1[i] + dp2[i] - 1);
    return maxi;
}
```

Number of Longest Increasing Subsequences
```
int findNumberOfLIS(vector<int>& arr) {
    int n = arr.size();
    vector<int> dp(n, 1);
    vector<int> ct(n, 1);
    int maxi = 1;
    for (int i = 0; i < n; i++) {
        for (int prev_index = 0; prev_index < i; prev_index++) {
            if (arr[prev_index] < arr[i] && dp[prev_index] + 1 > dp[i]) {
                dp[i] = dp[prev_index] + 1;
                ct[i] = ct[prev_index];
            } 
            else if (arr[prev_index] < arr[i] && dp[prev_index] + 1 == dp[i]) {
                ct[i] = ct[i] + ct[prev_index];
            }
        }
        maxi = max(maxi, dp[i]);
    }
    int numberOfLIS = 0;
    for (int i = 0; i < n; i++) {
        if (dp[i] == maxi) numberOfLIS += ct[i];
    }
    return numberOfLIS;
}
```

Matrix Chain Multiplication	
```
```	

Minimum Cost to Cut the Stick		
```
```	

Burst Balloons	
```
```	

Evaluate Boolean Expression to True		
```
```	

Palindrome Partitioning		
```
int dp[2001];

bool isPalindrome(int l,int r,string &s){
    while(l<r){
        if(s[l]!=s[r]) return false;
        l++;
        r--;
    }
    return true;
}

int f(int ind,int n,string s){
    if(ind==n) return 0;
    if(dp[ind]!=-1) return dp[ind];
    int minVal=INT_MAX;
    for(int i=ind;i<n;i++){
        if(isPalindrome(ind,i,s)){
            minVal=min(minVal,f(i+1,n,s));
        }
    }
    return dp[ind]=1+minVal;
}

int minCut(string s) {
    memset(dp,-1,sizeof(dp));
    int n=s.size();
    for(int ind=n-1;ind>=0;ind--){
        int minVal=1e9;
        for(int i=ind;i<n;i++){
            if(isPalindrome(ind,i,s)){
                minVal=min(minVal,f(i+1,n,s));
            }
        }
        dp[ind]=1+minVal;
    }
    
    return dp[0]-1;
}
```	

Partition Array for Maximum Sum		
```
int dp[501];

int f(int ind,int n,vector<int>& a,int k){
    if(ind==n) return 0;
    int maxVal=0;
    int maxAns=0;
    if(dp[ind]!=-1) return dp[ind];
    for(int i=ind;i<min(ind+k,n);i++){
        maxVal=max(maxVal,a[i]);
        maxAns=max(maxAns,(i-ind+1)*maxVal + f(i+1,n,a,k));
    }
    return dp[ind]=maxAns;
}

int maxSumAfterPartitioning(vector<int>& a, int k) {
    memset(dp,-1,sizeof(dp));
    return f(0,a.size(),a,k);
}
```	

Maximum Rectangle Area with all 1's	
```
void left(vector<int> &l,vector<int> &h){
    stack<int> s;
    for(int i=0;i<h.size();i++){
        while(!s.empty() && h[i]<=h[s.top()]) s.pop();
        if(!s.empty()) l[i]=s.top();
        s.push(i);
    }
}

void right(vector<int> &r,vector<int> &h){
    stack<int> s;
    for(int i=h.size()-1;i>=0;i--){
        while(!s.empty() && h[i]<=h[s.top()]) s.pop();
        if(!s.empty()) r[i]=s.top();
        s.push(i);
    }
}

int largestRectangleArea(vector<int>& h) {
    vector<int> l(h.size(),-1);
    vector<int> r(h.size(),h.size());
    left(l,h);
    right(r,h);
    int ans=0;
    for(int i=0;i<h.size();i++){
        ans=max(ans,h[i]*(r[i]-l[i]-1));
    }
    return ans;
}

int maximalRectangle(vector<vector<char>>& m) {
    int ans=0;
    vector<vector<int>> g(m.size(),vector<int>(m[0].size(),0));
    for(int j=0;j<m[0].size();j++){
        int c=0;
        for(int i=0;i<m.size();i++){
            if(m[i][j]=='1') c++,g[i][j]=c;
            else c=0;
        }
    }
    for(auto it:g){
        ans=max(ans,largestRectangleArea(it));
    }
    return ans;
}
```	

Count Square Submatrices with All Ones
```
```	


# Trie
