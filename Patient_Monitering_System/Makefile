PROJECT_NAME = box
SRC = SRC/test.c\
SRC/insert.c\
SRC/display.c\
SRC/search.c\
SRC/max_height.c\
SRC/specific_color.c\
unity/unity.c

INC =./unity

$(PROJECT_NAME).out: $(SRC)
	gcc $^ -I $(INC) -o $@

test: $(PROJECT_NAME).out
	./$(PROJECT_NAME).out

analysis:
	cppcheck $(SRC)

memcheck: $(PROJECT_NAME).out
	valgrind ./$(PROJECT_NAME).out

coverage:${PROJECT_NAME}.out
	gcc -fprofile-arcs -ftest-coverage $(SRC) -I $(INC) -o $(PROJECT_NAME).out
	./${PROJECT_NAME}.out
	gcov -a $(SRC)

codesize:${PROJECT_NAME}.out
	size ./${PROJECT_NAME}.out

clean:
		rm -rf *.out *.o documentation/html *.gcov *.gcda *.gcno
