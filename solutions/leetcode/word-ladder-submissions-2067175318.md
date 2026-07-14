# word ladder/submissions/2067175318

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:
    int ladderLength(string beginWord, string endWord, vector<string>& wordList){

        int n= wordList.size();
        int m= beginWord.size();

        unordered_set<string>st (wordList.begin(), wordList.end());

        if(!st.count(endWord)){
            return 0;
        }

        int dist=1;

        queue<string> q;
        q.push(beginWord);

        while(!q.empty()){

            int size= q.size();

            while(size--){
                string temp = q.front();
                q.pop();

                if(temp== endWord){
                    return dist;
                }

                for(auto s: wordList){
                    int a=0;
                    for(int i=0; i<m; i++){
                        if(temp[i]== s[i]){
                            a++;
                        }
                    }
                    if(m-a==1 && st.count(s)){
                        st.erase(s);
                        q.push(s);
                    }

                }
            }
            dist++;
        }
        return 0;









































    //     int w= beginWord.size();
    //     int s= wordList.size();
    //     unordered_set<string> list(wordList.begin(), wordList.end());
    //     queue<pair<string, int>>q;
    //     q.push({beginWord, 1});
    //     while(!q.empty()){
    //         string word= q.front().first;
    //         int count= q.front().second;
    //         q.pop();
        
    //     if(word==endWord){
    //         return count;
    //     }
    //     for( int i=0; i<w;i++){
    //         string temp= word;
    //         for( char ch='a'; ch<='z';ch++){
    //             temp[i]= ch;
    //             if(list.find(temp)!=list.end()){
    //             q.push({temp,count+1});
    //             list.erase(temp);
    //     }

    //     }
    //     }
        
    //     }
    //     return 0;

    }
};
```
