// you can also use imports, for example:
// import java.util.*;

// you can write to stdout for debugging purposes, e.g.
// System.out.println("this is a debug message");

class Solution {
    public int solution(int N) {
        int totalzero = 0; //1이 나오기 전까지의 제일 많은 0의 개수? 1과 1사이의 제일 많은 0의 개수?
        int zero = 0;   //1이 나오기 전까지의 0의개수
        
         String zeroStr = Integer.toBinaryString(N); //검색해보니 수를 2진수 문자열로 변환시켜주는 함수가 Integer 클래스에 있어서 사용
        
         
        char zeroChar[] = zeroStr.toCharArray(); //변환된 2진수를 다시 배열로 저장하는 함수 사용(char형은 무조건 한개의 문자값만 저장 가능)
        
         
        for(int i=0;i<zeroChar.length; i++){    //2진수 배열
            if(zeroChar[i] == '1'){ // i번째 배열의 값이 1일 때 (char형이므로 '' 로 감싸야 한다. 아니면 인식할 수 없음 이것때문에 삽질 많이함;;)
                if(zero > totalzero) {
                    totalzero = zero; // 1이 나왔을 때 지금까지 올라갔던 0의 개수와 그 전의 최대 0의 개수와 비교해서 갱신
                }
                zero = 0;   //갱신 후 다시 0의 개수는 0으로 초기화한다
            }else{
                zero++; // i번째 배열의 값이 1이 아닐때 1이 나오기 전의 0의 개수를 1 더한다.
            }
        }
         
        return totalzero;
    }
}