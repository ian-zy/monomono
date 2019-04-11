println('hello jenkins')

def files = currentBuild.changeSets
                .collectMany { it.items }
                .collectMany { it.affectedFiles }
                .collect { it.path }
            
println("Files Changed:")
println(files)
