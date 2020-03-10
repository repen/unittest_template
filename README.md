## Template unittest. Python 3+

### Example
```
import unittest

class TestService(unittest.TestCase):

    @classmethod
    def setUpClass(cls):
        cls.users = [10000, 10001, 10002]
        # print("create user list id")

    def setUp(self):
        pass

    def test_in_user(self):
        self.assertTrue( 10000 in self.users )
        self.assertFalse( self.user in self.users )

        for x in range(1000):
            self.assertFalse(x in self.users)

    @classmethod
    def tearDownClass(cls):
        cls.users = []
        # print("End! clear user list")

def suite():
    suite = unittest.TestSuite()
    suite.addTest(TestService('test_in_user'))
    return suite


if __name__ == '__main__':
    runner = unittest.TextTestRunner()
    runner.run(suite())
```
---
```
python -m unittest
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK
```