```java
class MyCircularDeque {
    int head = 0;//头指针
    int tail = 0;//尾指针
    int length = 0;//当前长度
    int size = 0;//容量
    int [] queue = null;//数组实现

    /** Initialize your data structure here. Set the size of the deque to be k. */
    public MyCircularDeque(int k) {
    
        this.size = k;
        queue = new int[k];
    }
    
    /** Adds an item at the front of Deque. Return true if the operation is successful. */
    public boolean insertFront(int value) {
        if(isFull())
            return false;
        else{
            //从头部指针位置顺序插入
            queue[head]=value;
            //考虑超出数组边界情况
            head = (head+size-1)%size;
            length++;
            return true;
        }
    }
    
    /** Adds an item at the rear of Deque. Return true if the operation is successful. */
    public boolean insertLast(int value) {
        if(isFull())
            return false;
        else{
            
            tail= (tail+1)%size;
            queue[tail]=value;
            length++;
            return true;
        }
    }
    
    /** Deletes an item from the front of Deque. Return true if the operation is successful. */
    public boolean deleteFront() {
         if(isEmpty()){
    		return false;
    	}else{
    		head = (head+1)%size;		//队头后移
             length--;
    		return true;
    	}
    }
    
    /** Deletes an item from the rear of Deque. Return true if the operation is successful. */
    public boolean deleteLast() {
        if(isEmpty()){
    		return false;
    	}else{
    		tail = (tail+size-1)%size;//队尾前移
            length--;
    		return true;
    	}
    }
    
    /** Get the front item from the deque. */
    public int getFront() {
          if(isEmpty())
    		return -1;
    	else  
    		return queue[(head+1)%size];
    }
    
    /** Get the last item from the deque. */
    public int getRear() {
        if(isEmpty())
    		return -1;
    	else  
    		return queue[tail]; 
    }
    
    /** Checks whether the circular deque is empty or not. */
    public boolean isEmpty() {
        if( length==0 )	
    		return true;
    	else  
    		return false;
    }
    
    /** Checks whether the circular deque is full or not. */
    public boolean isFull() {
          if(length==size)
    		return true;
    	else  
    		return false;
    }
}

/**
 * Your MyCircularDeque object will be instantiated and called as such:
 * MyCircularDeque obj = new MyCircularDeque(k);
 * boolean param_1 = obj.insertFront(value);
 * boolean param_2 = obj.insertLast(value);
 * boolean param_3 = obj.deleteFront();
 * boolean param_4 = obj.deleteLast();
 * int param_5 = obj.getFront();
 * int param_6 = obj.getRear();
 * boolean param_7 = obj.isEmpty();
 * boolean param_8 = obj.isFull();
 */
 ```