# comment_stars

## Description



## Columns

| Name | Type | Default | NOT NULL | Children | Parents | Comment |
| ---- | ---- | ------- | -------- | -------- | ------- | ------- |
| id | uuid | uuid_generate_v4() | true |  |  |  |
| user_id | integer |  | true |  |  |  |
| comment_post_id | integer |  | true |  | [comments](comments.md)  |  |
| comment_user_id | integer |  | true |  | [comments](comments.md) [users](users.md)  |  |
| created | timestamp without time zone |  | true |  |  |  |
| updated | timestamp without time zone |  | false |  |  |  |

## Constraits

| Name | Type | Def |
| ---- | ---- | --- |
| comment_stars_user_id_comment_post_id_comment_user_id_key | UNIQUE | UNIQUE (user_id, comment_post_id, comment_user_id) |
| comment_stars_user_id_post_id_fk | FOREIGN KEY | FOREIGN KEY (comment_post_id, comment_user_id) REFERENCES comments(post_id, user_id) |
| comment_stars_user_id_fk | FOREIGN KEY | FOREIGN KEY (comment_user_id) REFERENCES users(id) |

## Indexes

| Name | Def |
| ---- | --- |
| comment_stars_user_id_comment_post_id_comment_user_id_key | CREATE UNIQUE INDEX comment_stars_user_id_comment_post_id_comment_user_id_key ON public.comment_stars USING btree (user_id, comment_post_id, comment_user_id) |

---

> Generated by [tbls](https://github.com/k1LoW/tbls)