# Git ��ɾ�

git init : git ����
git branch branch_name : �귣ġ ����
git checkout branch_name : �귣ġ ����
git checkout -t remote_path/branch_name : ���� �귣ġ ����
git branch -d branch_name : �귣ġ �����ϱ�
git push remote_name ? delete branch_name : ���� �귣ġ ���� ( git push origin ? delete gh-pages )
git branch -r : ���� �귣ġ ��Ϻ���
git branch -a : ���� �귣ġ ��Ϻ���
git commit -m ��Ŀ�� ���롱 : Ŀ�� �޽��� ����
git push romote_name branch_name : add�ϰ� commit�� �ڵ� git server�� ������ (git push origin master)
git pull : git ������ �� �귣ġ���� �ֽ� ���� �޾ƿ���

git reset ? hard HEAD^ : commit�� ���� �ڵ� ����ϱ�
git reset ? soft HEAD^ : �ڵ�� �츮�� commit�� ����ϱ�
git reset ? merge : merge ����ϱ�
git reset ? hard HEAD && git pull : git �ڵ� ������ ��� �޾ƿ���
git stash / git stash save ��description�� : �۾��ڵ� �ӽ�����
git stash pop : ���������� �ӽ������� �۾��ڵ� ��������
git branch ? set-upstream-to=remote_path/branch_name : git pull no tracking info �����ذ�