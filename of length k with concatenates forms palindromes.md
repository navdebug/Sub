def check(n):
    rev=0 
    t=n 
    while(t!=0):
        rem=t%10 
        rev=rev*10+rem 
        t//=10  
    if rev==n:
        return True 
    
    return False 
def findsum(arr,k):
    i=0 
    num=0 
    while(i<k):
        num=num*10+arr[i] 
        i+=1 
    if (check(num)): 
        return 0 
    for j in range(i,len(arr)): 
        num=(num%(pow(10,k-1)))*10+arr[j]  
        if (check(num)):
            return j-k+1 
    return -1 
if __name__=='__main__':
    n,k=input().split()
    n,k=int(n),int(k) 
    arr=list(map(int,input().split())) 
    ans=findsum(arr,k) 
    if (ans==-1):
        print(-1) 
    else:
        for i in range(ans,ans+k):
            print(arr[i],end=" ")
    
    
        
