#include<iostream>
using namespace std;
class saddle
{
    int mat[5][5],r,c,i,j,k,l,ind;
public:
    saddle()
    {
        int r=c=i=j=k=l=ind=0;
    }
    void accept();
    void disp();
    void matrix();
};

void saddle::accept()
{
    cout<<"Enter the number of rows of matrix:";
    cin>>r;
    cout<<"\n Enter the number of columns of matrix:";
    cin>>c;
    cout<<"\n Enter the elements of the matrix \n";
    for(i=0; i<r; i++)
    {
        for(j=0; j<c; j++)
        {
            cin>>mat[i][j];
        }
    }
}
void saddle::disp()
{
    cout<<"\n  :Matrix:\n";
    for(i=0; i<r; i++)
    {
        for(j=0; j<c; j++)
        {
            cout<<mat[i][j]<<"\t";
        }
        cout<<"\n";
    }
}

void saddle::matrix()
{
    int small[5];
     small[i]=0;
    for(i=0; i<r; i++)
    {
        small[i] = mat[i][0];

        for(j=1; j<c; j++)
        {
            if(small[i]> mat[i][j])
            {
                small[i] = mat[i][j];
                ind = j;
            }
        }
            for(k=0;k<c;k++)
            if(small[i]<mat[k][ind])
            break;
            if(k==c)
            {
                cout<<"The saddle point is: "<<small[i];
            }
    }
}
        int main()
        {
            saddle s1;
            s1.accept();
            s1.disp();
            s1.matrix();
            return 0;
        }

