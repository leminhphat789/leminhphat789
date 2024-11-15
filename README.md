#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    int N, W;
    cin >> N >> W;

    vector<int> trong_luong(N), gia_tri(N);
    for (int i = 0; i < N; i++) {
        cin >> trong_luong[i] >> gia_tri[i];
    }

vector<vector<long long> > dp(N + 1, vector<long long>(W + 1, 0));

    for (int i = 0; i < N; i++) {
        for (int w = 0; w <= W; w++) {
            if (w >= trong_luong[i]) {
                dp[i + 1][w] = max(dp[i][w], dp[i][w - trong_luong[i]] + gia_tri[i]);
            } else {
                dp[i + 1][w] = dp[i][w];
            }
        }
    }

    cout << dp[N][W] << endl;

    return 0;
}#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    int N, W;
    cin >> N >> W;

    vector<int> trong_luong(N), gia_tri(N);
    for (int i = 0; i < N; i++) {
        cin >> trong_luong[i] >> gia_tri[i];
    }

vector<vector<long long> > dp(N + 1, vector<long long>(W + 1, 0));

    for (int i = 0; i < N; i++) {
        for (int w = 0; w <= W; w++) {
            if (w >= trong_luong[i]) {
                dp[i + 1][w] = max(dp[i][w], dp[i][w - trong_luong[i]] + gia_tri[i]);
            } else {
                dp[i + 1][w] = dp[i][w];
            }
        }
    }

    cout << dp[N][W] << endl;

    return 0;
}
