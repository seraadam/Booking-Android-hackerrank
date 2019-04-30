## Problem

```
Android: Implement findViewById method  given that View extends ViewGroup
```
## Solution
```java
private View findViewById(ViewGroup root, int id) {
        if (root.getId() == id) return root;
        int ccount = root.getChildCount();

        for (int i = 0; i< ccount ; i++) {
            View c = root.getcAt(i);
            if (c.getId() == id) return c;
            if (c instanceof ViewGroup) {
                View v = findViewById((ViewGroup) c, id);
                if (v != null) return v;
            }
        }
        return null;
    }
```
