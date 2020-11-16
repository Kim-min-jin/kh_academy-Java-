```java
public class Application {

    public static void main(String[] args) {
        // 리스코프 치환 원칙!
        final Stack<Integer> stack = new ArrayStack<>();

        stack.push(10);
        stack.push(20);
        stack.push(30);
        stack.push(40);
        stack.push(50);
        stack.push(60);

        System.out.println(stack.pop());
        System.out.println(stack.pop());
        System.out.println(stack.pop());
        System.out.println(stack.pop()); 
        System.out.println(stack.pop());
        System.out.println(stack.pop());
        System.out.println(stack.pop()); 
        System.out.println(stack.isEmpty());
    }
}
```

```java
import java.util.Arrays;

public class ArrayStack<T> implements Stack<T> {

    private static final int DEFAULT_SIZE = 5;

    private Object[] array = new Object[DEFAULT_SIZE];
    private int top = 0;
    private int currentCapacity = DEFAULT_SIZE;

    @Override
    public void push(T value) {
        ensureCapacity();
        array[top++] = value;
    }

    private void ensureCapacity() {
        // 1. 배열이 꽉찼는지 검사
        if (top >= DEFAULT_SIZE) {
            // 2. 꽉찬 경우 배열을 늘림
            array = Arrays.copyOf(array, currentCapacity * 2);
            // 3. 현재 최대 용량 값 늘림
            currentCapacity *= 2;
        }
    }

    @SuppressWarnings("unchecked")  // 앎.
    @Override
    public T pop() {
        if (top <= 0) {
            return null;
        }
        top -= 1;
        final Object result = array[top];
        array[top] = null;
        return (T) result;
    }

    @Override
    public boolean isEmpty() {
        return array[0] == null;
    }
}
```

```java
public class DoublyLinkedList<T> implements List<T> {

    private Node<T> head;
    private Node<T> tail;

    @Override
    public int size() {
        return 0;
    }

    @Override
    public boolean isEmpty() {
        return false;
    }

    @Override
    public T get(int index) {
        return null;
    }

    @Override
    public boolean contains(T element) {
        return false;
    }

    @Override
    public boolean add(T element) {
        return false;
    }

    @Override
    public boolean remove(T element) {
        return false;
    }

    @Override
    public void clear() {

    }

    private static class Node<T> {
        private T data;
        private Node<T> next;
        private Node<T> prev;
    }
}
```

```java
import java.util.LinkedList;
import java.util.List;


public class LinkedListStack<T> implements Stack<T> {

    private final List<T> stack = new LinkedList<>();

    @Override
    public void push(T value) {
        stack.add(value);
    }

    @Override
    public T pop() {
        final int size = stack.size();
        if (size <= 0) {
            return null;
        }
        return stack.remove(size - 1);
    }

    @Override
    public boolean isEmpty() {
        return stack.isEmpty();
    }
}

```

```java
public interface List<T> {

    /**
     * @return 요소의 개수를 반환
     */
    int size();

    /**
     * @return 요소가 없으면 true
     */
    boolean isEmpty();

    /**
     * @param index 찾을 요소의 위치
     * @return 요소
     */
    T get(int index);

    /**
     * 
     * @param element 찾을 요소
     * @return 찾을 요소가 존재하면 true
     */
    boolean contains(T element);

    /**
     * @param element 추가할 요소
     * @return 추가 성공 시 true
     */
    boolean add(T element);

    /**
     * @param element 삭제할 요소
     * @return 삭제 시 true
     */
    boolean remove(T element);

    /**
     * 요소 모두 삭제
     */
    void clear();
}
```

```java
public interface Stack<T> {

	/**
	 * @param value 값을 넣는다
	 */
	void push(T value);
	
	
	

	/**
	 * @return 꼭대기에 있는 값을 꺼낸다
	 */
	T pop();

	/**
	 * @return 비어있으면 true
	 */
	boolean isEmpty();
}



```