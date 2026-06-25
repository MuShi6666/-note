# java后端rag知识库的表结构

### ai_agent

``` sql
/*
 Navicat Premium Dump SQL

 Source Server         : 192.168.1.9
 Source Server Type    : PostgreSQL
 Source Server Version : 160013 (160013)
 Source Host           : 192.168.1.9:5432
 Source Catalog        : nexai
 Source Schema         : public

 Target Server Type    : PostgreSQL
 Target Server Version : 160013 (160013)
 File Encoding         : 65001

 Date: 25/06/2026 10:39:47
*/


-- ----------------------------
-- Table structure for ai_rag
-- ----------------------------
DROP TABLE IF EXISTS "public"."ai_rag";
CREATE TABLE "public"."ai_rag" (
  "id" varchar(32) COLLATE "pg_catalog"."default" NOT NULL,
  "alias" varchar(255) COLLATE "pg_catalog"."default",
  "dept_id" varchar(32) COLLATE "pg_catalog"."default" NOT NULL,
  "tenant_id" varchar(32) COLLATE "pg_catalog"."default" NOT NULL,
  "icon" varchar(256) COLLATE "pg_catalog"."default",
  "title" varchar(128) COLLATE "pg_catalog"."default",
  "description" varchar(512) COLLATE "pg_catalog"."default",
  "slug" varchar(128) COLLATE "pg_catalog"."default",
  "vector_id" varchar(32) COLLATE "pg_catalog"."default",
  "vector_store_name" varchar(32) COLLATE "pg_catalog"."default",
  "embed_model_id" varchar(32) COLLATE "pg_catalog"."default",
  "create_time" timestamp(6),
  "create_user_id" varchar(20) COLLATE "pg_catalog"."default",
  "update_time" timestamp(6),
  "update_user_id" varchar(20) COLLATE "pg_catalog"."default",
  "options" text COLLATE "pg_catalog"."default",
  "rerank_model_id" varchar(32) COLLATE "pg_catalog"."default",
  "search_engine_enable" bool,
  "full_search_type" varchar(32) COLLATE "pg_catalog"."default",
  "english_name" varchar(256) COLLATE "pg_catalog"."default",
  "deleted" int8,
  "ocr_model_id" varchar(64) COLLATE "pg_catalog"."default",
  "chat_model_id" varchar COLLATE "pg_catalog"."default"
)
;
COMMENT ON COLUMN "public"."ai_rag"."id" IS 'Id';
COMMENT ON COLUMN "public"."ai_rag"."alias" IS '别名';
COMMENT ON COLUMN "public"."ai_rag"."dept_id" IS '部门ID';
COMMENT ON COLUMN "public"."ai_rag"."tenant_id" IS '租户ID';
COMMENT ON COLUMN "public"."ai_rag"."icon" IS 'ICON';
COMMENT ON COLUMN "public"."ai_rag"."title" IS '标题';
COMMENT ON COLUMN "public"."ai_rag"."description" IS '描述';
COMMENT ON COLUMN "public"."ai_rag"."slug" IS 'URL 别名';
COMMENT ON COLUMN "public"."ai_rag"."vector_id" IS '向量数据库类型';
COMMENT ON COLUMN "public"."ai_rag"."vector_store_name" IS '向量数据集';
COMMENT ON COLUMN "public"."ai_rag"."embed_model_id" IS 'Embedding 模型ID';
COMMENT ON COLUMN "public"."ai_rag"."create_time" IS '创建时间';
COMMENT ON COLUMN "public"."ai_rag"."create_user_id" IS '创建用户ID';
COMMENT ON COLUMN "public"."ai_rag"."update_time" IS '最后一次修改时间';
COMMENT ON COLUMN "public"."ai_rag"."update_user_id" IS '最后一次修改用户ID';
COMMENT ON COLUMN "public"."ai_rag"."options" IS '其他配置';
COMMENT ON COLUMN "public"."ai_rag"."rerank_model_id" IS '重排模型id';
COMMENT ON COLUMN "public"."ai_rag"."search_engine_enable" IS '是否启用搜索引擎';
COMMENT ON COLUMN "public"."ai_rag"."english_name" IS '英文名称';
COMMENT ON COLUMN "public"."ai_rag"."ocr_model_id" IS '图片理解模型ID';
COMMENT ON COLUMN "public"."ai_rag"."chat_model_id" IS '文本理解模型ID';
COMMENT ON TABLE "public"."ai_rag" IS '知识库';

-- ----------------------------
-- Indexes structure for table ai_rag
-- ----------------------------
CREATE UNIQUE INDEX "tb_ai_knowledge_alias_uindex" ON "public"."ai_rag" USING btree (
  "alias" COLLATE "pg_catalog"."default" "pg_catalog"."text_ops" ASC NULLS LAST
);

-- ----------------------------
-- Primary Key structure for table ai_rag
-- ----------------------------
ALTER TABLE "public"."ai_rag" ADD CONSTRAINT "ai_rag_pkey1" PRIMARY KEY ("id");
```
