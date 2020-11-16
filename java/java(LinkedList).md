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
public class LinkedList<T> implements List<T> {

	private Node<T> head;

	@Override
	public int size() {
		// 1. 머리가 없는 경우
		if(head == null) {
			return 0;
		}

		// 2. 머리가 있는 경우
		int size = 1;
		Node<T> pointer = head;
		while(pointer!= null) {
			
			size++;
			pointer = head.getNext();
		}

		return size;

	}

	@Override
	public boolean isEmpty() {
		return head == null;
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
		final Node<T> newNode = new Node<>(element, null);
		// 1. head가 없는 경우
		if (head == null) {
			head = newNode;
			return true;
		}

		// 2. head가 있는 경우
		Node<T> pointer = head;
		while (pointer.getNext() != null) {
			pointer = pointer.getNext();
		}
		pointer.setNext(newNode);
		return true;
	}

	@Override
	public boolean remove(T element) {
		return false;
	}

	@Override
	public void clear() {
		head = null;
	}

	private static class Node<T> {
		private T data;
		private Node<T> next;

		public Node(T data, Node<T> next) {
			this.data = data;
			this.next = next;
		}

		public Node<T> getNext() {
			return next;
		}

		public void setNext(Node<T> next) {
			this.next = next;
		}
	}
}

```

```java
public class Application {

    public static void main(String[] args) {
        final List<String> list = new LinkedList<>();
        list.add("hi");
        list.add("bye");
        list.add("byebye");
        System.out.println(list.size());
    }
}
```