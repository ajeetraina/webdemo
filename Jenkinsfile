node("master") {
    docker.withRegistry('hub.docker.com', 'ajeetraina') {
    
        git url: "https://github.com/ajeetraina/webdemo, credentialsId: 'ajeetraina'
    
        sh "git rev-parse HEAD > .git/commit-id"
        def commit_id = readFile('.git/commit-id').trim()
        println commit_id
    
        stage "build"
        def app = docker.build "webdemo"
    
        stage "publish"
        app.push 'master'
        app.push "${commit_id}"
    }
}
