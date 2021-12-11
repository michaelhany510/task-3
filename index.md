# const
### The const keyword specifies that a variable's value is constant and tells the compiler to prevent the programmer from modifying it.
#### ex:

    const int N = 5;
    int main()
    {
        //N = 4;//error: cannot modify a const variable value.
    }

### you can specify the size of an array using a const variable
#### ex:


    const int MAX = 25;
    int arr[MAX];
## using const with pointers

### 1_ pointer variable pointing to a const value
#### ex:

    int main()
    {
        int var = 10,n=10;
        const int * befPtr = new int;

        befPtr = &var;

        //    *befPtr = 5; syntax error because putting (const) before (int*) makes the pointer in the read only mode
        //    which prevents you from modifying the content.

        befPtr = &n;//you can point to another location in memory.
    }

### 2_ const pointer variable point to the value

#### ex:

    int main()
    {
        int *const aftPtr = new int;
        //    aftPtr = &var; gives an error because you cannot let the pointer points 
        //    to another location of memory except the one it points to from the first.
        *aftPtr = 5; //you can for sure change the content.
    }

### 3_ const pointer variable point to constant value

#### ex:

    int main()
    {
        int var = 5;
        //the following declaration prevents you from neither pointing
        //to another location in the memory nor changing the contents.
        const int* const aftAndBef = &var;
        //*aftAndBef = 5 ;error: you cannot modify the content
        //aftAndBef = &var;error: you cannot point to another location.
    }

### const with member functions
#### declaring a method as const means that the method is in the read only mode which means you cannot modify any of the attributes of the members.
#### ex:
    class entity
    {
        private:
            int mx,my;
            mutable int var;
        public:
            //const here puts your method in read only mode, so you cannot
            //change the contents of the attributes unless its mutable
            int getX() const
            {
                var = 2;
                //mx = 5;//gives an error because it is not mutable.
            }
    };

### const with struct
#### using const objects means using const attributes as well except for the mutable ones
#### ex:
    const struct
    {
        int n1;
        mutable int n2;
    } x = {0, 0};      // const object with mutable member
    int main()
    {
        //  x.n1 = 4; // error: member of a const object is const
        x.n2 = 4; // ok, mutable member of a const object isn't const
    }

# ampersand &
## it can be used as a:
### 1_ bitwise and operator &
### it does the bitwise and operation over two operands(char or int).
#### ex:
    5 & 2 = 0
    6 & 2 = 2
    
### 2_ logical operator &&
#### it does the logical and operation and returns true if all operands are true and false if just one of them is false

### 3_ it can be put before variables to return it's address in the memory.
#### ex:

    int x = 5;
    cout<< &x << ' ';//prints the address of x in the memory.




