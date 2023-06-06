# Week7-Automated Testing

# Insertion Sort（插入排序）

```java
import java.util.Arrays;

public class InsertionSort {

    public static void main(String[] args) {
        int[] arr = { 1, 5, 2, 9 };
        insertionSort(arr);
        System.out.println("排序后的数组为：" + Arrays.toString(arr)); // 排序后的数组为：[1, 2, 5, 9]
    }

    public static void insertionSort(int[] arr) {
        int n = arr.length;
        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }
            arr[j + 1] = key;
        }
    }
}
```

* 我们可以用打扑克牌来解释插入排序算法。
* 假设我们手上有一副无序的扑克牌，现在我们需要将它们排序。首先，我们将第一张牌放在桌子上，这张牌相当于已排序的子数组。接着，我们依次将剩下的牌插入到已排序的子数组中，以使整个数组都有序。

  具体来说，我们从第二张牌开始，依次将每张牌插入到已排序的子数组中。插入的过程是这样的：将当前牌与已排序的子数组中的每张牌比较，如果当前牌的值比已排序的子数组中的牌的值小，那么就将已排序的子数组中的牌往后移动一位，直到找到一个位置，使得当前牌的值不小于该位置的牌的值，然后将当前牌插入到该位置中。
* 这个过程就像我们插入一张新的牌到已经排好序的一摞牌里面，不断地调整牌的位置，直到整副牌有序为止。
* 举个例子，假设我们手上有以下这些牌：`5, 2, 4, 6, 1, 3`​
* 我们首先将第一张牌 5 放在桌子上，它就是已排序的子数组。然后我们将第二张牌 2 插入到已排序的子数组中。由于 2 小于 5，我们需要将 5 往后移动一位，然后将 2 插入到第一个位置。此时已排序的子数组为：​`2, 5`​
* 接下来，我们将第三张牌 4 插入到已排序的子数组中。由于 4 小于 5，我们将 5 往后移动一位，然后将 4 插入到第二个位置。此时已排序的子数组为：`2, 4, 5`​
* 依此类推，我们继续将剩下的牌插入到已排序的子数组中，直到整副牌都有序为止。最终排序后的结果为：

  `1, 2, 3, 4, 5, 6`​

这就是插入排序的基本思路。

‍

```java
import java.util.Scanner;

public class Main {

    private static World world = new World("Middle Earth");

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int option;
        do {
            option = menu(scanner);
            switch (option) {
                case 1:
                    addHobbit(scanner);
                    break;
                case 2:
                    addWizard(scanner);
                    break;
                case 3:
                    displayWorld();
                    break;
                case 4:
                    moveEntities();
                    break;
                case 0:
                    System.out.println("Exiting program...");
                    break;
                default:
                    System.out.println("Invalid option. Please enter a valid option (0 to 4).");
                    break;
            }
        } while (option != 0);
    }

    private static int menu(Scanner scanner) {
        System.out.println("1. Add a Hobbit");
        System.out.println("2. Add a Wizard");
        System.out.println("3. Display World Information");
        System.out.println("4. Move all entities twice continuously");
        System.out.println("0. Stop");
        System.out.print("Enter one valid option (0 to 4): ");
        return scanner.nextInt();
    }

    private static void addHobbit(Scanner scanner) {
        System.out.print("Enter Hobbit name: ");
        String name = scanner.next();
        Hobbit hobbit = new Hobbit(name, 100);
        world.addEntity(hobbit);
        System.out.println("Hobbit added to World.");
    }

    private static void addWizard(Scanner scanner) {
        System.out.print("Enter Wizard name: ");
        String name = scanner.next();
        System.out.print("Enter Wizard age: ");
        int age = scanner.nextInt();
        Wizard wizard = new Wizard(name, age, 50);
        world.addEntity(wizard);
        System.out.println("Wizard added to World.");
    }

    private static void displayWorld() {
        System.out.println("World Name: " + world.getName());
        System.out.println("Entities:");
        for (Entity entity : world.getTeam()) {
            if (entity instanceof Hobbit) {
                System.out.println("# " + entity.getName() + " (health: " + entity.getHealth() + ")");
            } else if (entity instanceof Wizard) {
                System.out.println("@ " + entity.getName() + " (wisdom: " + ((Wizard) entity).getWisdom() + ")");
            }
        }
    }

    private static void moveEntities() {
        for (Entity entity : world.getTeam()) {
            entity.move();
        }
        for (Entity entity : world.getTeam()) {
            entity.move();
            if (entity instanceof Hobbit) {
                ((Hobbit) entity).decreaseHealth(5);
            } else if (entity instanceof Wizard) {
                ((Wizard) entity).decreaseWisdom(1);
            }
        }
        System.out.println("Entities moved twice continuously.");
    }
}

```
