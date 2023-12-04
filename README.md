#include<iostream>
using namespace std;

class Analysis {
    int id;
    int res;
public:
    void setData(int sid, int sres) {
        id = sid;
        res = sres;
    }
    void display() {
        cout << "\t" << id << "\t" << res << "\n";
    }
    friend void calculatePassFail(Analysis a[], int& pass, int& fail);
};

void calculatePassFail(Analysis a[], int& pass, int& fail) {
    pass = 0;
    fail = 0;
    for (int i = 0; i < 10; i++) {
        if (a[i].res == 1)
            pass++;
        else
            fail++;
    }
}

int main() {
    Analysis a[10];
    int sres, sid;
    for (int i = 0; i < 10; i++) {
        cout << "\n Enter Student ID : ";
        cin >> sid;
        cout << "\n Enter 1 for pass and 2 for Fail : ";
        cin >> sres;
        a[i].setData(sid, sres);
    }

    cout << "\n\tID " << "Result \n";
    for (int i = 0; i < 10; i++) {
        a[i].display();
    }

    int pass, fail;
    calculatePassFail(a, pass, fail);

    cout << "\n\tNo of Passed student :\t" << pass;
    cout << "\n\tNo of Failed student :\t" << fail;
    if (pass > 8)
        cout << "\n\tRaise Tuition..!";
    return 0;
}# Student-result-analysis-c-program
