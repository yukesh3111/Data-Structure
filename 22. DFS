#include <stdio.h>
#include <stdlib.h>

#define MAX_VERTICES 100

int n;
int adj[MAX_VERTICES][MAX_VERTICES];
int visited[MAX_VERTICES];

void dfs(int v) {
    int i;
    visited[v] = 1;
    printf("%d ", v);
    for (i = 0; i < n; i++) {
        if (adj[v][i] == 1 && !visited[i]) {
            dfs(i);
        }
    }
}

int main() {
    int i, j;
    scanf("%d", &n);
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &adj[i][j]);
        }
    }
    for (i = 0; i < n; i++) {
        visited[i] = 0;
    }
    dfs(0);
    return 0;
}
